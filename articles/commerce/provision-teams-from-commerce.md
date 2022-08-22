---
title: Obsługa Microsoft Teams z Dynamics 365 Commerce
description: W tym artykule opisano sposób inicjowania Microsoft Teams przy użyciu danych organizacyjnych z systemu Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 56d7cb6da5c359d3e93553adbdc70a4786c42648
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268981"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Obsługa Microsoft Teams z Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób inicjowania Microsoft Teams przy użyciu danych organizacyjnych z systemu Dynamics 365 Commerce.

Dynamics 365 Commerce oferuje łatwy sposób udostępniania zespołów, jeśli jeszcze nie skonfigurowałeś tam zespołów dla swoich sklepów detalicznych. Korzystając z dobrze zdefiniowanych informacji z Commerce, które chcesz używać w Teams, możesz pomóc pracownikom sklepu rozpocząć pracę w Teams. Te informacje obejmują hierarchię organizacyjną, nazwy sklepów, informacje o pracownikach oraz konta Azure Active Directory (Azure AD). 

Proces inicjowania obsługi Teams ma dwa główne kroki:

1. W Teams utwórz zespół dla każdego sklepu detalicznego i dodaj pracowników sklepu jako członków odpowiedniego zespołu. Jeśli pracownik jest skojarzony z więcej niż jednym sklepem detalicznym, przynależność do zespołu odzwierciedla ten fakt. Zostanie utworzony zespół komunikacji, który obejmuje menedżerów regionalnych jako członków, aby ułatwić publikowanie zadań z Teams.
1. Przekaż hierarchię organizacyjną z usług Commerce do Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Inicjowanie obsługi Teams w Commerce headquarters

Przed dostarczeniem Microsoft Teams należy wykonać następujące zadania:

- Potwierdź, że wszyscy menedżerowie regionalni są menedżerami ds. komunikacji.
- Potwierdź, że konto Azure każdego menedżera sklepu i pracownika zostało skojarzone z rekordem tego menedżera lub pracownika w programie Commerce Headquarters.

Aby obsługiwać Teams w centrali Commerce, wykonaj kroki opisane poniżej.

1. Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.
1. Na okienku akcji wybierz opcję **Obsługa teams**. Zostanie utworzone zadanie wsadowe o nazwie **Tworzenie zespołów**.
1. Przejdź do **Administracja systemu \> Zapytania \> Zadania wsadowe** i znajdź ostatnie zadanie z opisem Inicjowanie **Obsługa Teams**. Czekaj, aż to zadanie zakończy się.

> [!TIP]
> Jeśli żaden z menedżerów regionalnych, kierowników sklepów i pracowników sklepu nie został skojarzony z licencją zespołu, może zostać wyświetlony następujący komunikat o błędzie: „Nie można pobrać kategorii SKU odpowiedzialnych za aplikacje dla użytkownika” Aby rozwiązać ten problem, wybierz **Synchronizacja zespołów i członków** w okienku akcji.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Sprawdzanie poprawności inicjowania obsługi Teams w centrum administratora Teams

Aby sprawdzić poprawność inicjowania obsługi Microsoft Teams w centrum administratora Microsoft Teams, wykonaj następujące kroki.
    
1. Przejdź do [centrum administracyjnego Teams](https://admin.teams.microsoft.com/) i zaloguj się jako administrator twojej dzierżawy usług e-commerce.
1. W lewym okienku nawigacji wybierz pozycję **Teams**, aby je rozwinąć, a następnie wybierz pozycję **Zarządzaj zespołami**.
1. Potwierdź, że utworzono jeden zespół dla każdego sklepu detalicznego Commerce.
1. Wybierz zespół i potwierdź, że pracownicy sklepu dodano do niego jako członków.
1. W lewym okienku nawigacji wybierz pozycję **Użytkownicy** i potwierdź, że wszyscy pracownicy sklepu we wszystkich sklepach dodano jako użytkowników.

Na poniższej ilustracji pokazano przykład strony **Zarządzanie zespołami** w Centrum administratora Teams.

![Przykład strony Zarządzanie zespołami w centrum administratora Teams.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Przekaż hierarchię organizacyjną z Commerce do Teams
    
Hierarchii organizacyjnej Commerce można używać w Microsoft Teams do publikowania zadań dla wszystkich lub wybranych sklepów, które używają tej samej struktury hierarchii.

Aby przekazać hierarchię organizacyjną Commerce do Teams, wykonaj następujące kroki.
    
1. W Commerce przejdź do **Handel detaliczny i inny \> Ustawienia kanału \> Harmonogram integracji Microsoft Teams**.
1. Wybierz opcję **Pobierz hierarchię określania wartości docelowych**, a następnie wybierz pozycję **Sklepy detaliczne według regionów**, aby pobrać plik z hierarchią organizacyjną z wartościami rozdzielaymi przecinkami (CSV).
1. Zainstaluj moduł Microsoft Teams PowerShell, wykonać poniższe kroki w [Instalacja Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).
1. Po wyświetleniu monitu w oknie programu Teams PowerShell zaloguj się, używając konta administratora twojej dzierżawy Azure AD.
1. Aby przekazać plik CSV dla hierarchii docelowych, wykonaj kroki w temacie [Konfigurowanie hierarchii określania docelowego dla zespołu](/microsoftteams/set-up-your-team-hierarchy).

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Sprawdź, czy hierarchia organizacyjna została przekazane do Teams

Aby sprawdzić, czy hierarchia organizacyjna została przekazana do Microsoft Teams, wykonaj następujące kroki.

1. Zaloguj się do Teams jako kierownik ds. komunikacji.
1. W lewym okienku nawigacji wybierz pozycję **Zadania według programu Planner**.
1. Na karcie **Listy opublikowane** utwórz nową listę, która ma fikcyjne zadanie.
1. Wybierz opcję **Publikuj**. Hierarchia organizacyjna powinna być wyświetlana w polu **Wybór osoby, która ma zostać opublikowana** w oknie dialogowym, tak jak pokazano na przykładzie na poniższej ilustracji.

![Przykład hierarchii organizacyjnej w oknie dialogowym Wybierz osoby, które mają być publikowane.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie integracji Dynamics 365 Commerce i Microsoft Teams](commerce-teams-integration.md)

[Włączanie integracji Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md)

[Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams](map-stores-existing-teams.md)

[Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ](teams-integration-faq.md)

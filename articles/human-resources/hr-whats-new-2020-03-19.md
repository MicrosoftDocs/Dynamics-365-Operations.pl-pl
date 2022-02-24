---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (19 marca 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 19 marca 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 902539a5abecba6ad99718afbb37613838450032
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526872"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (19 marca 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3014. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Limity środowiska Human Resources są teraz oparte na zaktualizowanej licencji (394595)

Zmieniono limit liczby środowisk na projekt w usłudze Lifecycle Services (usługi LCS). Poprzedni limit to dwa środowiska. Limit liczby środowisk produkcji i piaskownicy, które można tworzyć dla Human Resources w usłudze LCS, jest obecnie oparty na zaktualizowanej licencji. W zależności od liczby zakupionych licencji można teraz utworzyć tyle środowisk, ile potrzeba, na projekt usługi LCS. Nowa licencja, zaktualizowana 1 lutego 2020, umożliwia klientom kupowanie dodatkowych środowisk. Aby uzyskać więcej informacji dotyczących wymagań licencyjnych dotyczących dodatkowych środowisk, zapoznaj się z [Przewodnik licencjonowania systemu Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Umożliwia wyświetlanie danych o wynagrodzeniach w wielu firmach dla pracowników i menedżerów (403904)

W obszarze roboczym **Zarządzanie funkcjami** włącz tę funkcję. Aby uzyskać więcej informacji, zobacz temat [Włączanie i wyłączanie funkcji zapoznawczych](hr-admin-manage-features.md#enable-or-disable-preview-features).

Po włączeniu tej funkcji menedżerowie mogą wyświetlać bezpośrednie i rozszerzone raporty o wynagrodzeniach bez konieczności logowania się się w firmie zatrudnienia. Historia pełnego wynagrodzenia jest dostępna z poziomu wszelkich zalogowanych firm, do których może uzyskać dostęp menedżer. Aby uzyskać więcej informacji, zajrzyj do [Przegląd samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Włączanie funkcji scalania globalnej książki adresowej (427189)

Można teraz scalić zduplikowane wpisy książki adresowej, zaznaczając zduplikowane rekordy i wybierając opcję **Scal** ze strony **Globalnej książki adresowej**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Nie można skorygować salda urlopu dla planu bez naliczeń utworzonego za pomocą funkcji Wielokrotnych typów urlopu (419635)

Można teraz skorygować salda dla planów urlopów utworzonych za pomocą funkcji **Wielokrotnych typów urlopu** w module Zarządzanie funkcjami.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Pole stanowiska głównego w WorkerPositionAssignmentEntity po zakończeniu zatrudnienia pracownika (420774)

W przypadku pracowników z zakończonym zatrudnieniem w jednostce jest wyświetlana pozycja podstawowa aktywna w momencie zakończenia pracy. W przypadku integracji nie będzie już tworzony zduplikowany rekord dla przypisania stanowiska pracownika etatowego. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>Rozwiązanie Common Data Service jest teraz dostępne z następującymi zmianami:

| opis | Zmiana |
| --- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | <ul><li>Dodano **Region wynagrodzenia**</li>|
| Dodano jednostkę **Wymiar stanowiska pracy** | <ul><li>Dodano **wymiary finansowe**</li>
| Zmiany jednostki **Pracownik** | <ul><li>Dodano **Kolejność w nazwisku**</li><li>Dodano **Pracuje z domu**</li><li>Dodano **Język**</li><li>Dodano **Data stażu pracy**</li><li>Dodano **Rocznica**</li><li>Dodano **Pierwotna data zatrudnienia**</li></ul> |
| Zmiany jednostki **Zatrudnienie** | <ul><li>Dodano **wymiary finansowe**</li><li>Dodano **Powód rozwiązania umowy**</li><li>**Data zakończenia** zmieniona z **daty przejścia**</li><li>Dodano **Okres próbny**</li></ul> |
| Zmiany jednostki **Adres Pracownika** | <ul><li>Dodano **Ulica**</li><li>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</li></ul> |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | <ul><li>**Typ planu wynagrodzeń o zmiennej wysokości**</li><li>**Plan wynagrodzeń o zmiennej wysokości**</li><li>**Reguły wypłat**</li><li>**Poziom planu wynagrodzeń o zmiennej wysokości**</li></ul> |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | <ul><li>Dodano **jednostkę kalendarza pracy**</li></ul> |
| Nowa jednostka **Szczegół stanowiska listy płac** | <ul><li>Dodano **Szczegół stanowiska listy płac**</li></ul> |
| Nowa jednostka **Tytuł** | <ul><li>Dodano **Tytuł**</li></ul>Nowa jednostka **tytułu** jest dołączona do Common Data Service, ale nie odwołuje się do w tej chwili do jednostek **stanowiska pracy** ani **Pozycji**. |

> [!NOTE]
> Wymiary finansowe dla obu stanowisk i zatrudnienia zapewniają jednokierunkową integrację aktualizacji z modułu Human Resources do usługi Common Data Service. Aktualizacje wymiarów finansowych nie są obecnie synchronizowane z usługi Common Data Service do modułu Human Resources.

W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach. Aby ręcznie zainstalować najnowsze rozwiązanie Common Data Service dla modułu Human Resources:

1.  Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).

2.  Wybierz opcję **Środowiska**.

3.  Znajdź środowisko, które chcesz uaktualnić. Środowisko powinno odpowiadać **nazwie środowiska** w sekcji **informacji programu Common Data Service** w formularzu **O** w usłudze Human Resources.

4.  Wybierz środowisko, aby wyświetlić szczegóły środowiska.

5.  Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry. Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.

6.  Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.

7.  Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>Podgląd SharePoint nie działa w niektórych środowiskach

Jeśli Podgląd dokumentów przechowywanych w SharePoint nie działa, spróbuj wykonać poniższą procedurę:

1. Sprawdź, czy konto użytkownika administratora zawiera wiadomość e-mail skojarzoną z rekordem użytkownika. Można przejrzeć te informacje na stronie **Użytkownik**. Jeśli poczta e-mail nie jest skonfigurowana, należy dodać wiadomość e-mail i dostawcę za pomocą dodatku OData dla programu Excel. Domyślnie adres e-mail nie jest obecny w projekcie programu Excel. Musisz edytować projekt programu Excel, dodać wszystkie pola, zastosować je i odświeżyć. Po wykonaniu tych kroków można zaktualizować konto administratora.

2. Gdy konto Administratora ma skojarzone konto e-mail, zaloguj się do modułu Human Resources z poświadczeniami administratora.

3. Aby uruchomić podgląd dokumentu, uzyskaj dostęp do załącznika SharePoint.

4. Zaloguj się przy użyciu konta innego użytkownika, które ma dostęp do załączników i sprawdź, czy podgląd działa zgodnie z oczekiwaniami.

## <a name="coming-soon"></a>Wkrótce

### <a name="platform-update-33"></a>Aktualizacja platformy Update 33

- Aplikacje dla całej strony (wersja zapoznawcza) — Ta funkcja podglądu, wymagająca włączenia funkcji zapisanych widoków, zezwala na dodawanie aplikacji Power Apps, a także aplikacji innych firm jako funkcji pełnej strony za pośrednictwem pulpitu nawigacyjnego.

- Zapisane widoki (wersja zapoznawcza) — Ta funkcja podglądu włącza zapisane widoki, które są znaczącym ulepszeniem podsystemu personalizacji. Ta funkcja umożliwia użytkownikom tworzenie wielu nazwanych zestawów personalizacji na stronę. Widoki można również publikować w rolach zabezpieczeń.

- Optymalizacja „jest jedną z” funkcji filtrowania — ta funkcja umożliwia zoptymalizowane działanie „jednej z” funkcji filtrowania, co ułatwia wprowadzanie wielu wartości filtrów, ma prostszy mechanizm usuwania pojedynczych lub wszystkich wartości filtrów, a ponadto ma bardziej zwartą i intuicyjną wizualizację wartości filtrów.

- Polecane pola — użytkownicy często muszą dodawać pola do siatki lub strony. Może to być trudne przy użyciu tak wielu dostępnych pól. Zamiast wyszukiwania na dużej liście, funkcja ta pozwala systemowi na wyłonienie listy zalecanych pól na podstawie tego, co użytkownicy dodają najczęściej, w podobnych scenariuszach.

- Domyślne akcje trwałe w siatkach — ta funkcja zapewnia, że domyślna akcja w siatce jest połączona z określoną kolumną w siatce, niezależnie od tego, czy kolumna ta jest przenoszona czy ukryta.

## <a name="new-production-release-cadence"></a>Nowa frekwencja wydania produkcyjnego

Począwszy od kwietnia, frekwencja wydwania nowych aktualizacji dla Human Resources przesunie się z cotygodniowej aktualizacji na aktualizację typu dwutygodniowego. Zapewni to wyrównanie przy użyciu zasad bezpiecznego wdrażania i zachowanie wysokich standardów stabilności i niezawodności w usłudze. W celu zweryfikowania pomyślnego wdrożenia na każdym etapie procesu umieszczamy dodatkowe testy i urządzenia kontrolne. Aby uzyskać więcej informacji o frekwencjji aktualizacji wersji, odwiedź [Proces aktualizacji](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>Wersja próbna

Następujące funkcje w wersji zapoznawczej są dostępne od 3 lutego 2020 r.:

- **Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)
---
title: Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych
description: Ten temat zawiera informacje o komórkowym obszarze roboczym Współpraca z dostawcami. Ten obszar roboczy pomaga Twoim dostawcom być na bieżąco z zamówieniami zakupu, które zostały im wysłane do zatwierdzenia. Mogą również wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: riluan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 5cd8a2b2db7147aca6bdc29ba15d99a619ddb4f8
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020843"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Współpraca z dostawcami**. Ten obszar roboczy pomaga Twoim dostawcom być na bieżąco z zamówieniami zakupu, które zostały im wysłane do zatwierdzenia. Mogą również wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji mobilnej Finance and Operations.

## <a name="overview"></a>Omówienie 
Mobilny obszar roboczy **Współpraca z dostawcami** przekazuje dostawcom na bieżąco informacje o nowych zamówieniach zakupu, dzięki czemu widzą oni zamówienia zakupu i mogą na nie reagować w kliencie internetowym. 

>[!NOTE]
> Mobilny obszar roboczy powinien być używany jako dodatek do internetowego interfejsu współpracy z dostawcami, a nie zamiast niego. 

Twoi dostawcy mogą używać mobilnego obszaru roboczego **Współpraca z dostawcami** do wyświetlania nowych zamówień zakupu wysyłanych im do zatwierdzenia. Obszar pokazuje różne informacje z zamówień zakupu, takie jak produkty, ilości i żądane daty dostawy. W zależności od konfiguracji konkretnego dostawcy są dostępne również wybrane informacje o cenach. 

Użytkownik, który zaloguje się jako dostawca, będzie widział, na które zamówienia zakupu odpowiedziano, a które zamówienia zakupu wciąż oczekują na działania odbiorcy. Na przykład zamówienie zakupu może oczekiwać na działanie odbiorcy, ponieważ dostawca zaproponował inną datę dostawy, a odbiorca jeszcze się na nią nie zgodził. Dostawca będzie także widział listę zamówień zakupu, które zostały potwierdzone, ale nie zostały jeszcze dostarczone. 

Aby odpowiedzieć na zamówienie zakupu, dostawca musi użyć internetowego interfejsu współpracy z dostawcami, który jest dostępny w kliencie internetowym. Tam dostawca również uzyska więcej informacji o zamówieniu, takich jak załączone dokumenty, adresy dostawy dla poszczególnych wierszy oraz opłaty, które musi ponieść. 

Dostawcy posiadający specjalną rolę zabezpieczeń mogą zobaczyć osoby kontaktowe zarejestrowane na swoich kontach dostawców. Ta sama rola zabezpieczeń pozwala dostawcy wyświetlić stan każdego przesłanego wniosku użytkownika. 

Internetowego interfejsu współpracy z dostawcami w kliencie internetowym należy używać do tworzenia nowych kontaktów i przesyłania wniosków o nowych użytkowników. 

Mobilny obszar roboczy **Współpraca z dostawcami** pozwala dostawcy wykonywać następujące zadania:

-   Wyświetlanie nowych zamówień zakupu wysłanych do dostawcy.
-   Wyświetlanie zamówień zakupu, na które dostawca odpowiedział i które oczekują na działanie ze strony odbiorcy.
-   Wyświetlanie zamówień zakupu, które zostały potwierdzone, ale nie zostały jeszcze w pełni przyjęte.
-   Wyświetlanie informacji o osobach kontaktowych zarejestrowanych na koncie dostawcy. (To zadanie wymaga dodatkowej roli zabezpieczeń).
-   Wyświetlanie informacji o wniosku użytkownika przesłanym przez dostawcę i monitorowanie stanu tego wniosku.. (To zadanie wymaga dodatkowej roli zabezpieczeń).

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Warunki wstępne, jeśli jest używane Supply Chain Management
Jeśli w organizacji wdrożono rozwiązanie Supply Chain Management, administrator systemu musi opublikować mobilny obszar roboczy **Współpraca z dostawcami**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne. 

<table>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Jeśli używasz aktualizacji platformy 3, należy zainstalować poprawkę KB 3216943.</td>
<td>Administrator systemu</td>
<td>KB 3216943 to binarna aktualizacja, która jest wymagana, jeśli używasz aktualizacji platformy 3. W celu zainstalowania tej poprawki KB administrator systemu musi wykonać następującą procedurę:
<ol>
<li>Pobierz poprawkę KB 3216943 z usługi Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Zainstaluj poprawkę binarną, która jest dostarczana jako wdrażalny pakiet. Aby uzyskać informacje o tym, jak zastosować wdrażalny pakiet, zobacz <a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Stosowanie wdrażalnego pakietu</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4013633.</td>
<td>Administrator systemu</td>
<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Dostępne zapasy</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi LCS</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</li><li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Współpraca z dostawcami</strong> musi być opublikowany.</td><td>Administrator systemu</td>
<td>Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
<tr class="even">
<td>Użytkownik u dostawcy musi mieć dostęp do internetowego interfejsu współpracy z dostawcami w kliencie internetowym i skonfigurować użytkownika zarządzającego współpracą z dostawcą.</td><td>Specjaliści ds. zakupów i administrator systemu</td>
<td>Wykonaj kroki opisane w poniższych tematach, aby skonfigurować internetowy interfejs współpracy dostawcy i w nim pracować.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Używanie obszaru roboczego współpracy z dostawcami do pracy z zewnętrznymi dostawcami</a></li>
<li><a href="manage-vendor-collaboration-users.md">Zarządzanie użytkownikami portalu współpracy z dostawcami</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Konfigurowanie i obsługa współpracy z dostawcami</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Używanie obszaru roboczego współpracy z dostawcami do pracy z odbiorcami w rozwiązaniu Supply Chain Managements</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobieranie i instalowanie aplikacji mobilnej Finance and Operations:

-   [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.
4.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
5.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

    [![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Używanie mobilnego obszaru roboczego Współpraca z dostawcami
Po wybraniu obszaru roboczego **Współpraca z dostawcami** pojawią się następujące opcje.

![Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych](./media/vendor-collaboration-mobile-app.png)

Obszar roboczy **Współpraca z dostawcami** zawiera następujące strony.

### <a name="contacts"></a>Kontakty
Na stronie **Kontakty** widać wszystkie osoby kontaktowe, które zostały skonfigurowane na koncie dostawcy. Jest tam imię i nazwisko osoby kontaktowej, główny adres e-mail oraz alias użytkownika, jeśli osoba kontaktowa ma alias. Ta strona wskazuje również, czy konto użytkownika osoby kontaktowej jest aktywne. Po zaznaczeniu osoby kontaktowej zobaczysz jej szczegóły, takie jak firmy, dla których ta osoba jest osobą kontaktową. Zostaną także wyświetlone informacje kontaktowe, takie jak numer telefonu lub alternatywny adres e-mail.

### <a name="user-requests"></a>Wnioski użytkownika
Na stronie **Wnioski użytkowników** są wyświetlane wszystkie wnioski użytkowników przesłane przez Ciebie za pośrednictwem internetowego interfejsu współpracy z dostawcami. Możesz również śledzić stan ich rozpatrywania. Po wybraniu wniosku użytkownika możesz zobaczyć, o co wnioskowano, dodać lub zdezaktywować użytkownika, zmienić zabezpieczenia oraz zobaczyć, o które role zabezpieczeń poproszono dla użytkownika.

### <a name="purchase-orders-ready-for-review"></a>Zamówienia zakupu gotowe do przejrzenia
Strona **Zamówienia zakupu gotowe do przeglądu** pozwala zobaczyć wszystkie zamówienia zakupu wysłane przez odbiorcę, na które jeszcze nie udzielono odpowiedzi. Można wyświetlić wybrane informacje dotyczące zamówienia, na przykład o które produkty wnioskowano i kiedy należy je dostarczyć. W zależności od konfiguracji dostawcy są dostępne również wybrane informacje o cenach.

Można również zobaczyć, czy zamówienie zakupu ma notatki i załączniki. Jednak aby otworzyć notatki i załączniki, należy użyć internetowego interfejsu współpracy z dostawcami w kliencie internetowym. Wybierz opcję **Wiersz zamówienia zakupu**, aby wyświetlić wszystkie wiersze ze szczegółami. Dla każdego wiersza wskaźnik pokaże, czy istnieją notatki lub załączniki albo czy adres dostawy różni się od wyświetlanego w nagłówku.

Aby odpowiedzieć na zamówienie zakupu, należy użyć klienta internetowego współpracy z dostawcami dostępnego w kliencie internetowym.

### <a name="awaiting-customer-action"></a>Oczekiwanie na akcję odbiorcy
Strona **Oczekiwanie na akcję odbiorcy** pozwala znaleźć zamówienia zakupu, na które Ty lub inna w Twojej firmie z dostępem do modułu Współpraca z dostawcami udzieliliście odpowiedzi. Zamówienia zakupu są widoczne na tej liście tylko wtedy, gdy odbiorca musi wykonać jedną z następujących czynności wobec zamówienia zakupu:

-   Jeśli zamówienie zakupu zostało odrzucone, odbiorca musi zaktualizować lub anulować pierwotne zamówienie, po czym wysłać je ponownie. Jeśli zamówienie zakupu zostanie wysłane ponownie, przestanie być widoczne na stronie **Oczekiwanie na akcję odbiorcy**.
-   Jeśli zamówienie zakupu zostało zaakceptowane ze zmianami, odbiorca musi zaktualizować oryginalne zamówienie i wysłać je ponownie do przejrzenia albo zaktualizować zgodnie ze zmianami i natychmiast potwierdzić. W obu przypadkach zamówienie zakupu przestanie być widoczne na stronie **Oczekiwanie na akcję odbiorcy**.
-   Jeśli zamówienie zakupu zostało zaakceptowane, ale nadal jest widoczne na stronie **Oczekiwanie na akcję odbiorcy**, oznacza to, że nie zostało automatycznie potwierdzone w trakcie akceptacji. Teraz czeka, aż pracownik działu zakupów zmieni mu stan na **Potwierdzone**. Zazwyczaj zamówienie zakupu uważa się za porozumienie między odbiorcą a dostawcą z chwilą zaakceptowania zamówienia przez dostawcę. W efekcie aktualizacja do stanu **Potwierdzone** jest zazwyczaj tylko formalnością.

Po wybraniu zamówienia zakupu pojawiają się dodatkowe informacje o odpowiedzi. Widać szczegóły wierszy i odpowiedzi do każdego wiersza. Stan wiersza pokazuje, której z poniższych odpowiedzi udzielono:

-   Zaakceptowano
-   Odrzucona
-   Zaakceptowano ze zmianami
-   Zastąpiono/Substytut
-   Podziel do harmonogramu/Wiersz harmonogramu

Należy zauważyć, że pole **Dostarczanie** otrzymuje wartość **Tak** lub **Nie**, aby wskazać, czy towary z wierszy zostaną dostarczone. Towary określone w wierszu mogą nie zostać dostarczone z następujących przyczyn:

- Wiersz został odrzucony.
- Dokonano zastąpienia i nie oczekuje się, że oryginalny wiersz zostanie dostarczony w sposób określony w otrzymanym zamówieniu.
- Wiersz został podzielony na wiele wierszy harmonogramu i nie oczekuje się, że oryginalny wiersz zostanie dostarczony w sposób określony w otrzymanym zamówieniu.

Są wyświetlane wszelkie zmiany wprowadzone w odpowiedzi na wiersz zamówienia. Nie są jednak wyświetlane przekazane notatki ani załączniki. Aby otworzyć notatki i załączniki, należy użyć internetowego interfejsu współpracy z dostawcami w kliencie internetowym.

### <a name="open-confirmed-orders"></a>Otwarte potwierdzone zamówienia
Gdy zamówienie zakupu zostanie potwierdzone przez odbiorcę (tzn. jego stan zostanie zmieniony na **Potwierdzone**), pojawi się jako otwarte potwierdzone zamówienie. Pozostanie na tej liście do momentu, aż zostanie zarejestrowane jako przyjęte przez odbiorcę.

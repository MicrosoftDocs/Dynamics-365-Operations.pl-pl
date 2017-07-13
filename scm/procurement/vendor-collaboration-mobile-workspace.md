---
title: "Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych"
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Współpraca z dostawcami. Ten obszar roboczy pomaga Twoim dostawcom być na bieżąco z zamówieniami zakupu, które zostały im wysłane do zatwierdzenia. Mogą również wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 20e4c77bc47bffc3474559e3b9933b87e947e178
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych
<a id="vendor-collaboration-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Współpraca z dostawcami**. Ten obszar roboczy pomaga Twoim dostawcom być na bieżąco z zamówieniami zakupu, które zostały im wysłane do zatwierdzenia. Mogą również wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.

## Przegląd
<a id="overview" class="xliff"></a> 
Mobilny obszar roboczy **Współpraca z dostawcami** przekazuje dostawcom na bieżąco informacje o nowych zamówieniach zakupu, dzięki czemu widzą oni zamówienia zakupu i mogą na nie reagować w kliencie internetowym usługi Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. 

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

## Wymagania wstępne
<a id="prerequisites" class="xliff"></a>
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r.
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., administrator systemu musi opublikować mobilny obszar roboczy **Współpracy z dostawcami**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
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
<li>Zainstaluj poprawkę binarną, która jest dostarczana jako wdrażalny pakiet. Aby uzyskać informacje o tym, jak zastosować wdrażalny pakiet, zobacz <a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Stosowanie wdrażalnego pakietu</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4013633.</td>
<td>Administrator systemu</td>
<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Dostępne zapasy</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi LCS</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li><li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Współpraca z dostawcami</strong> musi być opublikowany.</td><td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
<tr class="even">
<td>Użytkownik u dostawcy musi mieć dostęp do internetowego interfejsu współpracy z dostawcami w kliencie internetowym i skonfigurować użytkownika zarządzającego współpracą z dostawcą.</td><td>Specjaliści ds. zakupów i administrator systemu</td>
<td>Wykonaj kroki opisane w poniższych tematach, aby skonfigurować internetowy interfejs współpracy dostawcy i w nim pracować.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Używanie obszaru roboczego współpracy z dostawcami do pracy z zewnętrznymi dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Zarządzanie użytkownikami portalu współpracy z dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Konfigurowanie i obsługa współpracy z dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Używanie obszaru roboczego współpracy z dostawcami do pracy z odbiorcami w programie Finance and Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## Pobieranie i instalowanie aplikacji mobilnej
<a id="download-and-install-the-mobile-app" class="xliff"></a>

Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

-   [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## Logowanie do aplikacji mobilnej
<a id="sign-in-to-the-mobile-app" class="xliff"></a>
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Microsoft Dynamics 365.
4.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
5.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

    [![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Używanie mobilnego obszaru roboczego Współpraca z dostawcami
<a id="use-the-vendor-collaboration-mobile-workspace" class="xliff"></a>
Po wybraniu obszaru roboczego **Współpraca z dostawcami** pojawią się następujące opcje.

![Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych](./media/vendor-collaboration-mobile-app.png)

Obszar roboczy **Współpraca z dostawcami** zawiera następujące strony.

### Kontakty
<a id="contacts" class="xliff"></a>
Na stronie **Kontakty** widać wszystkie osoby kontaktowe, które zostały skonfigurowane na koncie dostawcy. Jest tam imię i nazwisko osoby kontaktowej, główny adres e-mail oraz alias użytkownika, jeśli osoba kontaktowa ma alias. Ta strona wskazuje również, czy konto użytkownika osoby kontaktowej jest aktywne. Po zaznaczeniu osoby kontaktowej zobaczysz jej szczegóły, takie jak firmy, dla których ta osoba jest osobą kontaktową. Zostaną także wyświetlone informacje kontaktowe, takie jak numer telefonu lub alternatywny adres e-mail.

### Wnioski użytkownika
<a id="user-requests" class="xliff"></a>
Na stronie **Wnioski użytkowników** są wyświetlane wszystkie wnioski użytkowników przesłane przez Ciebie za pośrednictwem internetowego interfejsu współpracy z dostawcami. Możesz również śledzić stan ich rozpatrywania. Po wybraniu wniosku użytkownika możesz zobaczyć, o co wnioskowano, dodać lub zdezaktywować użytkownika, zmienić zabezpieczenia oraz zobaczyć, o które role zabezpieczeń poproszono dla użytkownika.

### Zamówienia zakupu gotowe do przejrzenia
<a id="purchase-orders-ready-for-review" class="xliff"></a>
Strona **Zamówienia zakupu gotowe do przeglądu** pozwala zobaczyć wszystkie zamówienia zakupu wysłane przez odbiorcę, na które jeszcze nie udzielono odpowiedzi. Można wyświetlić wybrane informacje dotyczące zamówienia, na przykład o które produkty wnioskowano i kiedy należy je dostarczyć. W zależności od konfiguracji dostawcy są dostępne również wybrane informacje o cenach.

Można również zobaczyć, czy zamówienie zakupu ma notatki i załączniki. Jednak aby otworzyć notatki i załączniki, należy użyć internetowego interfejsu współpracy z dostawcami w kliencie internetowym. Wybierz opcję **Wiersz zamówienia zakupu**, aby wyświetlić wszystkie wiersze ze szczegółami. Dla każdego wiersza wskaźnik pokaże, czy istnieją notatki lub załączniki albo czy adres dostawy różni się od wyświetlanego w nagłówku.

Aby odpowiedzieć na zamówienie zakupu, należy użyć klienta internetowego współpracy z dostawcami dostępnego w kliencie internetowym.

### Oczekiwanie na akcję odbiorcy
<a id="awaiting-customer-action" class="xliff"></a>
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

### Otwarte potwierdzone zamówienia
<a id="open-confirmed-orders" class="xliff"></a>
Gdy zamówienie zakupu zostanie potwierdzone przez odbiorcę (tzn. jego stan zostanie zmieniony na **Potwierdzone**), pojawi się jako otwarte potwierdzone zamówienie. Pozostanie na tej liście do momentu, aż zostanie zarejestrowane jako przyjęte przez odbiorcę.


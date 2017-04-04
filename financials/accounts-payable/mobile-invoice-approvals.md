---
title: "Mobilność-faktura zatwierdzeń"
description: "Mobilne możliwości usługi Microsoft Dynamics 365 dla operacji Niech użytkownik biznesowy projektowania rozwiązań mobilnych. Dla zaawansowanych scenariuszy platformy Niech również deweloperzy rozszerzają możliwości zechcą. Aby przejść przez proces projektowania kilka scenariuszy jest najbardziej skutecznym sposobem, aby dowiedzieć się niektóre z nowych koncepcji na telefon komórkowy. Ten temat jest przeznaczony do zapewnienia praktycznego podejścia do projektowania scenariuszy mobilnych biorąc dostawcy zatwierdzenia faktur dla urządzeń przenośnych, jak w przypadku użycia. W tym temacie powinien ułatwić projektowanie inne warianty scenariusze i mogą być stosowane do inne scenariusze, które nie są związane z faktur od dostawcy."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Mobilność-faktura zatwierdzeń

Mobilne możliwości usługi Microsoft Dynamics 365 dla operacji Niech użytkownik biznesowy projektowania rozwiązań mobilnych. Dla zaawansowanych scenariuszy platformy Niech również deweloperzy rozszerzają możliwości zechcą. Aby przejść przez proces projektowania kilka scenariuszy jest najbardziej skutecznym sposobem, aby dowiedzieć się niektóre z nowych koncepcji na telefon komórkowy. Ten temat jest przeznaczony do zapewnienia praktycznego podejścia do projektowania scenariuszy mobilnych biorąc dostawcy zatwierdzenia faktur dla urządzeń przenośnych, jak w przypadku użycia. W tym temacie powinien ułatwić projektowanie inne warianty scenariusze i mogą być stosowane do inne scenariusze, które nie są związane z faktur od dostawcy.

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                                                            | opis                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Podręcznik mobilnych wstępnie odczytu                                                                                |(/ dynamics365/operacji/dev-itpro/mobile aplikacje / mobile-platform.md)                                                                                                  |
| Dynamics 365 dla operacji                                                                             | Środowisku Microsoft Dynamics 365 dla wersji operacji 1611 i Microsoft Dynamics dla operacji platformy aktualizacji 3 (listopad 2016)                   |
| Należy zainstalować poprawkę KB 3204341.                                                                              | Program Task recorder błędnie można nagrywać dwa polecenia Zamknij dla okien dialogowych listy rozwijanej, który jest ono zawarte w Dynamics 365 dla operacji aktualizacji platformy 3 (aktualizacja listopada 2016) |
| Należy zainstalować poprawkę KB 3207800.                                                                              | Ta poprawka umożliwia załączniki będą wyświetlane na klientów mobilnych, to jest zawarty w usłudze Dynamics 365 dla operacji aktualizacji platformy 3 (aktualizacja listopada 2016).           |
| Należy zainstalować poprawkę KB 3208224.                                                                              | Kod aplikacji dla aplikacji mobilnych dostawcy zatwierdzenia faktury, z którą jest ono zawarte w aplikacji Microsoft Dynamics AX 7.0.1 (maja 2016).                          |
| Android lub iOS lub urządzenie systemu Windows, które ma zainstalowany dla usługi Dynamics 365 dla operacji aplikacji mobilnej | Wyszukaj aplikację w magazynie odpowiednią aplikację.                                                                                                                     |

## <a name="introduction"></a>Wprowadzenie
Mobilne zatwierdzeń dla faktur od dostawcy wymagają trzech poprawek, które są wymienione w sekcji "Wymagania wstępne". Te poprawki nie zapewniają obszaru roboczego dla zatwierdzenia faktur. Aby dowiedzieć się, co obszar roboczy jest w kontekście mobilnych, odczytać mobilnych podręcznika, który jest wymieniony w sekcji "Wymagania wstępne". Obszar roboczy zatwierdzenia faktury muszą być zaprojektowane. 

Każda organizacja organizuje i określa jego procesu biznesowego dla faktur od dostawcy w inny sposób. Przed rozpoczęciem projektowania urządzeń przenośnych dla zatwierdzenia faktur dostawcy, należy rozważyć następujące aspekty procesu biznesowego. Chodzi o to aby korzystać z tych punktów danych w najszerszym możliwym zoptymalizowanie czynności użytkownika na urządzeniu.

-   Które pola z nagłówka faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?
-   Które pola z wierszy faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?
-   Ile wierszy faktury istnieją faktury? Zastosowanie reguły 80-20 tutaj i zoptymalizować 80 procent.
-   Będzie użytkowników chcesz zobaczyć zasady podziału księgowań (kodowanie fakturze) na urządzeniu przenośnym podczas opinii? Jeśli odpowiedź na to pytanie jest twierdząca, należy rozważyć następujące kwestie:
    -   Jak wielu księgowań (cena rozszerzona, podatków, opłat, podziały itd.) dostępne są dla wiersza faktury? Ponownie Zastosuj regułę 80-20.
    -   Czy faktur również mają zasad podziału księgowań w nagłówku faktury? Jeśli tak, te zasady podziału księgowań należy udostępnić na urządzeniu?

> [!NOTE]
> W tym temacie nie wyjaśniono, jak edytować zasady podziału księgowań, ponieważ ta funkcja aktualnie nie jest obsługiwany w scenariuszach mobilnych.

-   Będzie użytkownicy chcą wyświetlić załączniki dla faktury na urządzeniu?

Projekt rozwiązania mobilne umożliwiające zatwierdzenia faktur różnią się w zależności od odpowiedzi na te pytania. Celem jest optymalizacja obsługi dla procesu biznesowego na telefonie w organizacji. W pozostałej części tego tematu będziemy patrzeć na dwie odmiany scenariusz, które są oparte na różnych odpowiedzi na pytania poprzedniego. 

Jako wytyczne ogólne, podczas pracy z projektantem mobilnych upewnij się opublikować zmiany, aby zapobiec utracie aktualizacje.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Projektowanie scenariusz zatwierdzenia faktury prosty "contoso"
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atrybut scenariusza</th>
<th>Odbierz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Które pola z nagłówka faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?</td>
<td><ol>
<li>Nazwa dostawcy</li>
<li>Suma faktury</li>
<li>Faktura akonto</li>
<li>Numer faktury</li>
<li>Data faktury</li>
<li>Opis faktury</li>
<li>Termin</li>
<li>Waluta faktury</li>
</ol></td>
</tr>
<tr class="even">
<td>Które pola z wierszy faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?</td>
<td><ol>
<li>Kategoria zaopatrzenia</li>
<li>Ilość</li>
<li>Cena jednostkowa</li>
<li>Kwota netto wiersza</li>
<li>Wartość 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Ile wierszy faktury istnieją faktury? Zastosowanie reguły 80-20 tutaj i zoptymalizować 80 procent.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Będzie użytkowników chcesz zobaczyć zasady podziału księgowań (kodowanie fakturze) na urządzeniu przenośnym podczas opinii?</td>
<td>Tak</td>
</tr>
<tr class="odd">
<td>Jak wielu księgowań (cena rozszerzona, podatków, opłat i tak dalej), istnieją dla wiersza faktury? Ponownie Zastosuj regułę 80-20.</td>
<td>Cena rozszerzona: 2 podatku: 0 koszty: 0</td>
</tr>
<tr class="even">
<td>Czy faktur również mają zasad podziału księgowań w nagłówku faktury? Jeśli tak, te zasady podziału księgowań należy udostępnić na urządzeniu?</td>
<td>Nieużywane</td>
</tr>
<tr class="odd">
<td>Będzie użytkownicy chcą wyświetlić załączniki dla faktury na urządzeniu?</td>
<td>Tak</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Tworzenie obszaru roboczego

1.  W przeglądarce otwórz 365 Dynamics dla operacji i logowania.
2.  Po zalogowaniu, dołącz **& Tryb = mobilnych** do adresu URL, jak pokazano w przykładzie następujące i Odśwież stronę: https://&lt;yoururl&gt;/? cmp = usmf & mi = DefaultDashboard**& mode = mobilnych**
3.  Kliknij **ustawienia** (bieg) przycisk w prawym górnym rogu strony, a następnie kliknij **aplikacji mobilnej**. Projektant aplikacji mobilnej musi wykazać tak jak Task recorder pojawia się.
4.  Kliknij **Dodaj** do utworzenia nowego obszaru roboczego. W tym przykładzie nazwa obszaru roboczego **Moje zatwierdzenia**.
5.  Wprowadź opis.
6.  Wybierz kolor obszaru roboczego. Kolor obszaru roboczego zostanie wykorzystany do ogólnego stylu przenośnych dla tego obszaru roboczego.
7.  Wybierz ikonę dla obszaru roboczego.
8.  Kliknij **Sporządzono**
9.  Kliknij **obszaru roboczego opublikować** zapisać zmiany

### <a name="vendor-invoices-assigned-to-me"></a>Faktury od dostawcy przypisane do mnie

Pierwsza strona mobilnych należy zaprojektować jest listy faktur, które są przypisane do użytkownika w celu przeglądu. Aby zaprojektować tę stronę dla urządzeń przenośnych, użyj **VendMobileInvoiceAssignedToMeListPage** strony w usłudze Dynamics 365 dla operacji. Przed wykonaniem tej procedury, upewnij się, faktury dostawcy co najmniej jeden przypisany do użytkownika do przeglądu, i że wiersz faktury ma dwa dystrybucje. Ta konfiguracja spełnia wymagania dla tego scenariusza.

1.  W usłudze Dynamics 365 dla operacji adresu URL, zastąp nazwę elementu menu z **VendMobileInvoiceAssignedToMeListPage** otworzyć mobilnej wersji **oczekujące faktury od dostawcy przypisane do mnie** strony listy w **rozrachunków z dostawcami** modułu. W zależności od liczby faktur, które zostały w systemie przypisane do Ciebie na tej stronie pokaże tych faktur. Aby wyszukać określone faktury, można użyć filtru po lewej stronie. Jednak w tym przykładzie nie wymagają określonej faktury. Wymagamy tylko niektóre faktury przypisane do użytkownika, która ma zamiar umożliwić można projektować strony przenośnej. Nowe strony, które są dostępne zostały zaprojektowane specjalnie dla rozwoju mobilnych scenariusze dla faktury od dostawcy. W związku z tym należy użyć tych stron. Adres URL powinien przypominać następujący adres URL, a po jego wprowadzeniu, musi znajdować się strony, które przedstawiono na rysunku: https://&lt;yourURL&gt;/? cmp = usmf & mi =**VendMobileInvoiceAssignedToMeListPage**& mode = mobilnych [![oczekujące faktury od dostawcy przypisane do mnie strony](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
2.  Kliknij **ustawienia** (bieg) przycisk w prawym górnym rogu strony, a następnie kliknij **aplikacji mobilnej**
3.  Wybierz obszar roboczy i kliknij przycisk **Edycja**
4.  Kliknij **stronę Dodaj** do utworzenia pierwszej stronie dla urządzeń przenośnych.
5.  Wprowadź nazwę, takich jak **Moje faktury dostawcy**oraz opis, takich jak **faktury od dostawcy przypisane do mnie do przeglądu**.
6.  Click **Done**.
7.  W Projektancie mobilnych na **pola** kliknij przycisk **wybierz pola**. Kolumn na stronie listy musi przypominać poniższy rysunek. [![Kolumny na Oczekujące faktury od dostawcy przypisane do mnie strony](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
8.  Dodaj wymagane kolumny na stronie Lista wskazana do użytkowników w stronę dla urządzeń przenośnych. Zamówienie, w którym możesz dodać jest kolejność wyświetlania pól do użytkownika końcowego. Jedynym sposobem, aby zmienić kolejność pól będzie ponownie, wybierając wszystkie pola. Zgodnie z wymaganiami, w tym scenariuszu, ośmiu następujące pola są wymagane. Jednakże niektórzy użytkownicy warto rozważyć ośmiu pola zbyt wiele informacji na urządzeniu przenośnym. W związku z tym przedstawia najważniejsze pola w widoku listy dla urządzeń przenośnych. Pozostałe pola będą wyświetlane w widoku Szczegóły, które możemy zostaną zaprojektowane później. Teraz dodamy następujące pola. Kliknij znak plus (**+**) w tych kolumnach, aby dodać do strony przenośnej.
    1.  Nazwa dostawcy
    2.  Suma faktury
    3.  Faktura akonto
    4.  Numer faktury
    5.  Data faktury

    Po dodaniu pola strony przenośnej musi przypominać poniższy rysunek. [![Strony po dodaniu pól](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)
9.  Należy także dodać następujące kolumny teraz, tak, że możemy później włączyć akcje przepływu pracy.
    1.  Pokaż wykonać zadania
    2.  Pokaż delegowanie zadania
    3.  Pokaż zadanie przypomnieć
    4.  Pokaż zadanie odrzucenia
    5.  Pokaż żądania ukończenie zadania
    6.  Pokaż ponownie prześlij zadanie

10. Kliknij **Sporządzono** aby wyjść z trybu edycji.
11. Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
12. Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę.
13. Włącz **sumy na oczekujące dostawcy faktury wyświetlania listy faktur** w formularzu Parametry płatne konta w obszarze **faktury**. Należy zauważyć, że tylko po włączeniu tego parametru, Podsumowanie faktury będzie obliczany mają być wyświetlane na stronie listy faktur od dostawcy oczekujące. Jest to nowa funkcja w ramach wstępnie wymagane poprawki 3208224.

### <a name="vendor-invoice-details"></a>Szczegóły faktury dostawcy

Aby zaprojektować stronę szczegółów faktury dla urządzeń przenośnych, użyj **VendMobileInvoiceHeaderDetails** strony w usłudze Dynamics 365 dla operacji. Należy zauważyć, że w zależności od liczby faktur, które zostały w systemie, ta strona przedstawia najstarsze faktury (faktura, który został utworzony po raz pierwszy). Aby wyszukać określone faktury, można użyć filtru po lewej stronie. Jednak w tym przykładzie nie wymagają określonej faktury. Po prostu wymagamy niektóre dane faktury, tak, że możemy zaprojektować stronę dla urządzeń przenośnych. [![Strona przepływu pracy](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1.  W usłudze Dynamics 365 dla operacji adresu URL, zastąp nazwę elementu menu z **VendMobileInvoiceHeaderDetails**, aby otworzyć formularz
2.  Otwórz projektanta mobilne z **ustawienia** przycisk (sprzęt).
3.  Kliknij **edytować** przycisk, aby rozpocząć tryb edycji w obszarze roboczym.
4.  Wybierz ** Moje faktury dostawcy ** strony utworzony wcześniej, a następnie kliknij **edytować**.
5.  Na **pola** kliknij przycisk **siatki** nagłówka kolumny.
6.  Kliknij **właściwości**&gt;**Dodaj stronę**. **Uwaga:** po kliknięciu **siatki** nagłówek i dodać stronę relacji ze szczegółami strony odbywa się automatycznie.
7.  Wpisz tytuł strony, takich jak **faktury szczegóły**oraz opis, takich jak **wyświetlić nagłówek faktury i szczegółów wiersza**.
8.  Kliknij **wybierz pola**. Należy zauważyć, że zamówienia, w którym możesz dodać jest kolejność wyświetlania pól do użytkownika końcowego. Jedynym sposobem, aby zmienić kolejność pól będzie ponownie, wybierając wszystkie pola.
9.  Dodaj następujące pola z nagłówka, na podstawie wymagań dotyczących tego scenariusza:
    1.  Nazwa dostawcy
    2.  Suma faktury
    3.  Faktura akonto
    4.  Numer faktury
    5.  Data faktury
    6.  Opis faktury
    7.  Termin
    8.  Waluta faktury

10. Dodaj następujące pola z siatki linii na stronie:
    1.  Kategoria zaopatrzenia
    2.  Ilość
    3.  Cena jednostkowa
    4.  Kwota netto wiersza
    5.  Wartość 1099

11. Po dodaniu wszystkich pól z dwa poprzednie kroki, kliknij przycisk **Sporządzono**. Strona musi przypominać poniższy rysunek. [![Strony po dodaniu pól](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Kliknij **Sporządzono** aby wyjść z trybu edycji.
13. Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
14. Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę

### <a name="workflow-actions"></a>Akcje przepływu pracy

Aby dodać akcje przepływu pracy, użyj **VendMobileInvoiceHeaderDetails** strony w usłudze Dynamics 365 dla operacji. Aby otworzyć tę stronę, należy zastąpić nazwę elementu menu w adresie URL, tak jak poprzednio. Następnie otwórz projektanta mobilne z **ustawienia** przycisk (sprzęt). Wykonaj następujące kroki, aby dodać akcje przepływu pracy na stronie szczegółów.

1.  Kliknij **edytować** przycisk, aby rozpocząć tryb edycji w obszarze roboczym.
2.  Wybierz **faktury szczegóły** strona utworzony wcześniej, a następnie kliknij **edytować**.
3.  Na **akcje** kliknij przycisk **Dodaj akcję**.
4.  Wprowadź tytuł akcji, takich jak **Zatwierdź**oraz opis, takich jak **faktury Zatwierdź**. Należy zauważyć, że tytuł akcji, wprowadzony w tym miejscu staje się nazwę akcji, który jest wyświetlany w aplikacji mobilnej.
5.  Click **Done**.
6.  Kliknij **wybierz pola**.
7.  Przejść przez proces przepływu pracy na **VendMobileInvoiceHeaderDetails** strony i ukończyć akcji, który chcesz nagrać. Upewnij się, wprowadź komentarze przepływu pracy podczas tego procesu, tak aby pola komentarze wchodzi także korzystanie z urządzeń przenośnych.
8.  Po uruchomieniu akcji przepływu pracy, kliknij przycisk **Sporządzono** do ukończenia zadania wybierz pola.
9.  Kliknij **Sporządzono** aby wyjść z trybu edycji.
10. Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
11. Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę
12. Powtórz kroki od 3 do 11, aby zarejestrować wszystkie akcje wymagane przepływu pracy. Należy pamiętać, że wymóg ma faktury przypisane do użytkownika, które są w stanie udostępnić użytkownikowi, że idziesz do projektowania dla akcji przepływu pracy.
13. Otwórz Notatnik lub Microsoft Visual Studio i wklej następujący kod. Zapisz plik jako plik js. Ten kod wykonuje dwie czynności:
    1.  Ukrywa kolumny dodatkowe dotyczące przepływu pracy, które wcześniej dodano na stronie listy dla urządzeń przenośnych. Dodaliśmy tych kolumn, tak aby aplikacja ma tych informacji w kontekście i można wykonać następny krok.
    2.  Oparty na kroku przepływu pracy, który jest aktywny, to stosuje się logiki, aby pokazać tylko te akcje.

Należy zauważyć, że nazwy stron i inne formanty w kodzie JS musi być taka sama, z obszaru roboczego.

1.  Funkcja główne (metadataService, dataService, cacheService, $q) {powrócić {appInit: funkcja (appMetadata) {/ / ukrywa formanty, które muszą być obecne, ale nie są widoczne metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowAccept', {ukryte: true}); metadataService.configureControl (" Mój--faktur od dostawcy, 'ShowApprove', {ukryte: true}); metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowReject', {ukryte: true}); metadataService.configureControl (" Moje--faktur od dostawcy, 'ShowDelegate', {ukryte: true}); metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowRequestChange', {ukryte: true}); metadataService.configureControl (" Moje--faktur od dostawcy, 'ShowRecall', {ukryte: true}); metadataService.configureControl ("Mój--faktur od dostawcy, 'ShowComplete', {ukryte: true}); metadataService.configureControl (" Mój--faktur od dostawcy, 'ShowResubmit' { ukryty: true}); }, pageInit: funkcja (pageMetadata, params) {Jeśli (pageMetadata.Name == "Szczegóły faktury") {/ / Pokaż/Ukryj przepływu pracy akcji w oparciu o przepływie pracy krok metadataService.configureAction ("Akceptuj", {widoczne: true}); metadataService.configureAction ("Zatwierdzanie", {widoczne: true}); metadataService.configureAction ('Odrzuć' {widoczne: true}); metadataService.configureAction ("Delegate" {widoczne: true}); metadataService.configureAction ("żądania zmiany", {widoczne: true}); metadataService.configureAction ("Odwołania" {widoczne: true}); metadataService.configureAction ("Zakończ", {widoczne: true}); metadataService.configureAction ("Resubmit", {widoczne: true});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Przekaż plik kodu do obszaru roboczego, wybierając **Logic** kartę
3.  Kliknij **Sporządzono** aby wyjść z trybu edycji.
4.  Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
5.  Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę

### <a name="vendor-invoice-attachments"></a>Załączniki faktury dostawcy

1.  Kliknij **ustawienia** (bieg) przycisk w prawym górnym rogu strony, a następnie kliknij **aplikacji mobilnej**
2.  Kliknij **edytować** przycisk, aby rozpocząć tryb edycji w obszarze roboczym.
3.  Wybierz ** faktury szczegóły ** strony utworzony wcześniej, a następnie kliknij **edytować**.
4.  Ustaw **Zarządzanie dokumentami** opcji w celu **tak** jak pokazano poniżej. **Uwaga:** Jeśli nie ma żadnych wymagań wyświetlania załączników na urządzeniu przenośnym, można pozostawić tę opcję ustawi się na **nr**, która jest ustawieniem domyślnym.
5.  [![docmanagement](./media/docmanagement-216x300.png)](./media/docmanagement.png)
6.  Kliknij **Sporządzono** aby wyjść z trybu edycji.
7.  Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
8.  Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę

### <a name="vendor-invoice-line-distributions"></a>Dystrybucje wiersza faktur od dostawców

Wymagania dotyczące tego scenariusza Potwierdź było tylko liniowe dystrybucji, a fakturę zawsze będzie tylko jeden wiersz. Ponieważ w tym scenariuszu jest proste, czynności użytkownika na urządzeniu przenośnym, musi być tyle prosty, że użytkownik nie musi przeprowadzić drążenie kilka poziomów do wyświetlania dystrybucji. Faktury od dostawcy w usłudze Dynamics 365 dla operacji obejmują opcja wyświetlania wszystkich przydziałów z nagłówka faktury. To doświadczenie jest potrzebujemy mobilnych scenariusza. W związku z tym będziemy używać **VendMobileInvoiceAllDistributionTree** stronę do projektowania tej części scenariusza mobilnych. 

> [!NOTE] 
> Znając wymagania pomaga nam konkretne strony, które używać i jak dokładnie do optymalizacji dla urządzeń przenośnych dla użytkownika podczas projektowania scenariusza. W drugim scenariuszu użyjemy innej stronie pokazanie dystrybucji, ponieważ różnią się wymagania dotyczące tego scenariusza.

1.  W adresie URL Zastąp nazwę elementu menu, tak jak wcześniej. Wyświetlona strona powinna przypominać poniższy rysunek. [![Wszystkie strony dystrybucje](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)
2.  Otwórz projektanta mobilne z **ustawienia** przycisk (sprzęt).
3.  Kliknij **edytować** przycisk, aby rozpocząć tryb edycji w obszarze roboczym. **Uwaga:** widać, że dwie nowe strony były tworzone automatycznie. System tworzy te strony, ponieważ włączone zarządzanie dokumentami w poprzedniej sekcji. Można zignorować te nowe strony.
4.  Kliknij **Dodaj stronę**.
5.  Wpisz tytuł strony, takich jak **widoku ewidencjonowania aktywności**oraz opis, takich jak **widoku ewidencjonowania aktywności dla faktury**.
6.  Click **Done**.
7.  Na **pola** kliknij przycisk **wybierz pola**, zaznacz następujące pola ze strony dystrybucji, a następnie kliknij przycisk **Sporządzono**:
    1.  Ilość
    2.  Waluta
    3.  Konto księgowe

> [!NOTE] 
> Firma Microsoft nie wybrano **opis** kolumny z siatki dystrybucji, ponieważ wymagania dotyczące tego scenariusza potwierdził, że cena rozszerzona jest tylko kwota, która będzie dystrybucji dla. W związku z tym użytkownik nie będzie wymagać innego pola w celu określenia typu kwoty, to dla dystrybucji. Jednak w następnym scenariuszu firma Microsoft **będzie** korzystać z tych informacji, ponieważ wymagania dotyczące tego scenariusza Określa, że inne typy kwota dystrybucji (na przykład podatek od sprzedaży).
8.  Kliknij **Sporządzono** aby wyjść z trybu edycji.
9.  Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
10. Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę

**Uwaga:****widoku ewidencjonowania aktywności** stronę dla urządzeń przenośnych nie jest obecnie połączony z żadnym mobilnych stron, które zaprojektowano tak daleko. Ponieważ użytkownik powinien być może przejść do **widoku ewidencjonowania aktywności** strona z **faktury szczegóły** stronę na urządzeniu przenośnym, możemy zapewnić nawigacji z **faktury szczegóły** strony **widoku ewidencjonowania aktywności** strony. Możemy ustanowić tej nawigacji przy użyciu logiki dodatkowe za pomocą JavaScript.

1.  Otwórz plik js, który został utworzony wcześniej i dodać wyróżnione wiersze w następującym kodzie. Ten kod wykonuje dwie czynności:
    1.  Pomaga zagwarantować, że użytkownicy nie mogą przechodzić bezpośrednio z obszaru roboczego do **widoku ewidencjonowania aktywności** strony.
    2.  Ustanawia ona formant nawigacji z **faktury szczegóły** strony **widoku ewidencjonowania aktywności** strony.

> [!NOTE] 
> Nazwa strony i inne formanty w kodzie JS musi być taka sama, z obszaru roboczego.

1.  Funkcja główne (metadataService, dataService, cacheService, $q) {powrócić {appInit: funkcja (appMetadata) {/ / ukrywa formanty, które muszą być obecne, ale nie są widoczne metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowAccept', {ukryte: true}); metadataService.configureControl (" Mój--faktur od dostawcy, 'ShowApprove', {ukryte: true}); metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowReject', {ukryte: true}); metadataService.configureControl (" Moje--faktur od dostawcy, 'ShowDelegate', {ukryte: true}); metadataService.configureControl ("Moje--faktur od dostawcy, 'ShowRequestChange', {ukryte: true}); metadataService.configureControl (" Moje--faktur od dostawcy, 'ShowRecall', {ukryte: true}); metadataService.configureControl ("Mój--faktur od dostawcy, 'ShowComplete', {ukryte: true}); metadataService.configureControl (" Mój--faktur od dostawcy, 'ShowResubmit' { ukryty: true}); Ukrywanie stron nie ma zastosowania do głównego nawigacji metadataService.hideNavigation('View-accounting'); Łącze, aby wyświetlić metadataService.addLink rachunkowości ("-Szczegóły faktury, ' widok rachunkowości", "rachunkowości nav formantu widoku", "Widok rachunkowe", PRAWDA); }, pageInit: funkcja (pageMetadata, params) {Jeśli (pageMetadata.Name == "Szczegóły faktury") {/ / Pokaż/Ukryj przepływu pracy akcji w oparciu o przepływie pracy krok metadataService.configureAction ("Akceptuj", {widoczne: true}); metadataService.configureAction ("Zatwierdzanie", {widoczne: true}); metadataService.configureAction ('Odrzuć' {widoczne: true}); metadataService.configureAction ("Delegate" {widoczne: true}); metadataService.configureAction ("żądania zmiany", {widoczne: true}); metadataService.configureAction ("Odwołania" {widoczne: true}); metadataService.configureAction ("Zakończ", {widoczne: true}); metadataService.configureAction ("Resubmit", {widoczne: true});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Przekaż plik kodu do obszaru roboczego, wybierając **Logic** kartę, aby zastąpić poprzedni kod
3.  Kliknij **Sporządzono** aby wyjść z trybu edycji.
4.  Kliknij **ponownie** a **Sporządzono** aby zakończyć obszaru roboczego
5.  Kliknij **obszaru roboczego opublikować** Aby zapisać swoją pracę

### <a name="validation"></a>Weryfikacja

Z urządzenia przenośnego Otwórz aplikację i połączyć się z 365 Dynamics dla wystąpienia operacji. Upewnij się, zaloguj do firmy gdzie faktur od dostawcy są przypisane do użytkownika do recenzji. Można wykonać następujące czynności:

-   Zobacz **Moje zatwierdzenia** obszaru roboczego.
-   Drążenie do **Moje zatwierdzenia** obszar roboczy i zobacz **Moje faktury dostawcy** strony.
-   Drążenie do **Moje faktury dostawcy** strony i wyświetlić listę faktur, które są przypisane do użytkownika.
-   Drążenie do jednej faktury i Zobacz szczegóły nagłówka faktury i szczegółów wiersza.
-   Na stronie szczegółów zawiera sekcja Łącze do załączników i użyć to łącze, aby przejść do listy załączników i wyświetlić załączniki.
-   Na stronie Szczegóły, zobacz łącze do **Zobacz rachunkowości** strony i używać to łącze, aby przejść do strony dystrybucji i wyświetlania dystrybucji.
-   Na stronie szczegółów kliknij **akcje** menu na dole i wykonywać akcje przepływu pracy, które mają zastosowanie do etapu przepływu pracy.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Projektowanie scenariusz zatwierdzenia złożone faktury dla firmy Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atrybut scenariusza</th>
<th>Odbierz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Które pola z nagłówka faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?</td>
<td><ol>
<li>Nazwa dostawcy</li>
<li>Kwota faktury</li>
<li>Faktura akonto</li>
<li>Numer faktury</li>
<li>Data faktury</li>
<li>Opis faktury</li>
<li>Termin</li>
<li>Waluta faktury</li>
</ol></td>
</tr>
<tr class="even">
<td>Które pola z wierszy faktury będzie użytkownika chcesz zobaczyć w korzystanie z urządzeń przenośnych i w jakiej kolejności?</td>
<td><ol>
<li>Kategoria zaopatrzenia</li>
<li>Ilość</li>
<li>Cena jednostkowa</li>
<li>Kwota netto wiersza</li>
<li>Wartość 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Ile wierszy faktury istnieją faktury? Zastosowanie reguły 80-20 tutaj i zoptymalizować 80 procent.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Będzie użytkowników chcesz zobaczyć zasady podziału księgowań (kodowanie fakturze) na urządzeniu przenośnym podczas opinii?</td>
<td>Tak</td>
</tr>
<tr class="odd">
<td>Jak wielu księgowań (cena rozszerzona, podatków, opłat i tak dalej), istnieją dla wiersza faktury? Ponownie Zastosuj regułę 80-20.</td>
<td>Cena rozszerzona: 2 podatku: opłaty 2: 2</td>
</tr>
<tr class="even">
<td>Czy faktur również mają zasad podziału księgowań w nagłówku faktury? Jeśli tak, te zasady podziału księgowań należy udostępnić na urządzeniu?</td>
<td>Nieużywane</td>
</tr>
<tr class="odd">
<td>Będzie użytkownicy chcą wyświetlić załączniki dla faktury na urządzeniu?</td>
<td>Tak</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Ćwiczenia

Następujące zmiany może odbywać się w scenariuszu 1, zgodnie z wymaganiami w scenariuszu 2. Użyj tej sekcji jako ćwiczenie, które można wykonać w celach edukacyjnych.

1.  Ponieważ oczekuje więcej wierszy faktury w scenariuszu 2, pomocne będą następujące zmiany w projekcie zoptymalizowanie czynności użytkownika na urządzeniu przenośnym:
    1.  Zamiast przeglądania wierszy faktury na stronie szczegółów (jak w scenariuszu 1), użytkownicy mogą wybrać do wyświetlania wierszy na osobnej stronie mobilnych.
    2.  Ponieważ więcej niż jeden wiersz faktury jest oczekiwany w tym scenariuszu jeśli **VendMobileInvoiceAllDistributionTree** strona jest używana do projektowania strony dystrybucje dla urządzeń przenośnych (jak w scenariuszu 1), mogą być mylące dla użytkownika do skorelowania linie podziału. W związku z tym, użyj **VendMobileInvoiceLineDistributionTree** stronę do projektowania strony dystrybucji.
    3.  W idealnej sytuacji dystrybucje powinny być wykazywane w kontekście wiersza faktury w tym scenariuszu. W związku z tym upewnij się, że użytkownik może przejść do wiersza, aby zobaczyć stronę dystrybucje. Możliwości łącza strony należy użyć w celu ustalenia drążenia wskroś, tak samo, jak dla nagłówka i szczegóły stron w scenariuszu 1.

2.  Ponieważ więcej niż jeden typ kwoty oczekuje na rozkład w scenariuszu 2 (podatków, opłat i tak dalej), będzie przydatne do przedstawiania opisu typu Kwota. (Firma Microsoft pominąć te informacje w scenariuszu 1.)

## <a name="conclusion"></a>Wniosek
Mobilne platformy oraz możliwości aplikacji pozwalają projektować mobilnych scenariuszy, które są zoptymalizowane pod kątem podstawowej w organizacji użytkownika. W oparciu o przykłady, które znajdują się w tym temacie, można spróbować innych odmian i tworzyć różne doświadczenia, które spełniają szczególne potrzeby.



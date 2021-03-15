---
title: Zatwierdzanie faktur na urządzeniach przenośnych
description: Ten temat przedstawia praktyczne podejście do projektowania scenariuszy komórkowych na bazie procesu zatwierdzania faktur od dostawców na urządzeniach komórkowych.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1e18d26a4ccee195d09560c62b1fb1dd05750cfd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991363"
---
# <a name="mobile-invoice-approvals"></a>Zatwierdzanie faktur na urządzeniach przenośnych

[!include [banner](../includes/banner.md)]

Opcje mobilne pozwalają użytkownikom biznesowym na projektowanie środowiska mobilnego. W scenariuszach zaawansowanych platforma umożliwia również deweloperom rozszerzanie funkcjonalności zgodnie z potrzebami. Najbardziej skutecznym sposobem, aby poznać niektóre nowe koncepcje obsługi na telefonach komórkowych, jest przejście przez proces projektowania w kilku scenariuszach. Ten temat przedstawia praktyczne podejście do projektowania scenariuszy komórkowych na bazie procesu zatwierdzania faktur od dostawców na urządzeniach komórkowych. Ten temat powinien ułatwić projektowanie w innych wariantach scenariuszy i może być również wykorzystywany w innych scenariuszach, niezwiązanych z fakturami od dostawców.

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                                                            | opis                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Podręcznik wprowadzający do platformy komórkowej                                                                                |[Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | Środowisko, w którym zainstalowano wersję 1611 oraz aktualizację nr 3 platformy (z listopada 2016 r.)                   |
| Instalacja poprawki KB 3204341.                                                                              | Rejestrator zadań może błędnie nagrywać dwa polecenia Zamknij dla rozwijanych okien dialogowych; Poprawka jest dołączona do aktualizacji nr 3 platformy (aktualizacja z listopada 2016 r.). |
| Instalacja poprawki KB 3207800.                                                                              | Ta poprawka umożliwia wyświetlanie załączników na klientach mobilnych. Poprawka jest dołączona do aktualizacji nr 3 platformy (aktualizacja z listopada 2016 r.).           |
| Instalacja poprawki KB 3208224.                                                                              | Kod źródłowy aplikacji zatwierdzania faktur od dostawców na urządzeniach komórkowych; również w wersji 7.0.1 (z maja 2016 r.).                          |
| Urządzenie z systemem Android, iOS lub Windows, na którym zainstalowano aplikację. | Wyszukaj aplikację w odpowiednim sklepie z aplikacjami.                                                                                                                     |

## <a name="introduction"></a>Wprowadzenie
Aby można było zatwierdzać faktury od dostawców na urządzeniach komórkowych, należy zainstalować trzy poprawki wymienione w sekcji „Wymagania wstępne”. Te poprawki nie udostępniają obszaru roboczego dla zatwierdzania faktur. Aby się dowiedzieć, czym jest obszar roboczy w kontekście pracy na urządzeniach komórkowych, przeczytaj podręcznik o platformie komórkowej wymieniony w sekcji „Wymagania wstępne”. Obszar roboczy zatwierdzania faktur musi być zaprojektowany. 

Każda organizacja inaczej przygotowuje i definiuje proces biznesowy faktur od dostawców. Przed rozpoczęciem projektowania komórkowego środowiska obsługi zatwierdzenia faktur od dostawców należy rozważyć następujące aspekty procesu biznesowego. Chcemy, aby korzystać z tych punktów w najszerszym możliwym zakresie w celu zoptymalizowania środowiska użytkownika na urządzeniu.

-   Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?
-   Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?
-   Ile wierszy faktury istnieje w fakturze? Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.
-   Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym? Jeśli odpowiedź na to pytanie jest twierdząca, należy rozważyć następujące kwestie:
    -   Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty, podziały itd.) istnieje dla wiersza faktury? Tu również zastosuj regułę 80-20.
    -   Czy faktury mają również zasady podziału księgowań w nagłówku faktury? Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?

    > [!NOTE]
    > W tym temacie nie wyjaśniono, jak edytować zasady podziału księgowań, ponieważ ta funkcja aktualnie nie jest obsługiwana w scenariuszach mobilnych.

-   Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?

Projekt komórkowego środowiska obsługi zatwierdzania faktur będzie się różnił w zależności od odpowiedzi na te pytania. Celem jest optymalizacja środowiska obsługi procesu biznesowego na urządzeniach komórkowych w organizacji. W pozostałej części tego tematu przyjrzymy się dwóm wariantom scenariusza, które są oparte na różnych odpowiedziach na powyższe pytania. 

Jako ogólną wskazówkę należy pamiętać, aby podczas pracy w projektancie środowiska komórkowego „publikować” zmiany w celu uniknięcia utraty aktualizacji.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Projektowanie prostego scenariusza zatwierdzania faktur dla firmy Contoso
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
<td>Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</td>
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
<td>Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</td>
<td><ol>
<li>Kategoria zaopatrzenia</li>
<li>Ilość</li>
<li>Cena jednostkowa</li>
<li>Kwota netto wiersza</li>
<li>Wartość 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Ile wierszy faktury istnieje w fakturze? Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym?</td>
<td>Tak</td>
</tr>
<tr class="odd">
<td>Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty itd.) istnieje dla wiersza faktury? Tu również zastosuj regułę 80-20.</td>
<td>Cena rozszerzona: 2 Podatek: 0 Opłaty: 0</td>
</tr>
<tr class="even">
<td>Czy faktury mają również zasady podziału księgowań w nagłówku faktury? Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?</td>
<td>Nieużywane</td>
</tr>
<tr class="odd">
<td>Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?</td>
<td>Tak</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Tworzenie obszaru roboczego

1.  W przeglądarce i zaloguj się do aplikacji.
2.  Po zalogowaniu dołącz wyrażenie **&mode=mobile** do adresu URL, jak pokazano w przykładzie poniżej, i odśwież stronę: https://&lt;TwójadresURL&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**. Musi zostać wyświetlony projektant aplikacji komórkowych, tak jak się pojawia Rejestrator zadań.
4.  Kliknij przycisk **Dodaj**, aby utworzyć nowy obszar roboczy. W tym przykładzie nazwij obszar roboczy **Moje zatwierdzenia**.
5.  Wprowadź opis.
6.  Wybierz kolor dla obszaru roboczego. Kolor obszaru roboczego będzie stosowany do ogólnego stylu komórkowego środowiska obsługi w tym obszarze roboczym.
7.  Wybierz ikonę dla obszaru roboczego.
8.  Kliknij przycisk **Gotowe**.
9.  Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać zmiany.

### <a name="vendor-invoices-assigned-to-me"></a>Faktury od dostawcy przypisane do mnie

Pierwszą stroną środowiska mobilnego, jaką należy zaprojektować, jest lista faktur przypisanych użytkownikowi w celu weryfikacji. Aby zaprojektować tę stronę dla urządzeń przenośnych, użyj strony **VendMobileInvoiceAssignedToMeListPage** strony. Przed wykonaniem tej procedury upewnij się, że co najmniej jedna faktura od dostawcy jest Ci przypisana do weryfikacji, a wiersz tej faktury ma dwie dystrybucje. Ta konfiguracja spełnia wymagania tego scenariusza.

1.  W adresie URL zastąp nazwę elementu menu wyrażeniem **VendMobileInvoiceAssignedToMeListPage**, aby otwierać mobilną wersję strony listy **Oczekujące faktury od dostawcy — przypisane do mnie** w module **rozrachunków z dostawcami**. W zależności od liczby faktur, które zostały w systemie przypisane do Ciebie, na tej stronie będą wyświetlane te faktury. Aby znaleźć konkretną fakturę, możesz użyć filtru z lewej strony. Jednak w tym przykładzie nie potrzebujemy konkretnej faktury. Musisz mieć tylko przypisaną jakąś fakturę, co umożliwi Ci projektowanie strony mobilnej. Nowe strony, które są dostępne, zostały zaprojektowane specjalnie do tworzenia scenariuszy mobilnych dla faktur od dostawców. W związku z tym należy używać tych stron. Adres URL powinien przypominać poniższy adres URL, a po jego wprowadzeniu musi zostać wyświetlona strona przedstawiona na rysunku: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![Strona Oczekujące faktury od dostawcy — przypisane do mnie](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**.
3.  Zaznacz swój obszar roboczy i kliknij przycisk **Edytuj**.
4.  Kliknij przycisk **Dodaj stronę**, aby utworzyć pierwszą stronę dla urządzeń przenośnych.
5.  Wprowadź nazwę, taką jak **Moje faktury od dostawców**, oraz opis, taki jak **Faktury od dostawców przypisane mi do weryfikacji**.
6.  Kliknij przycisk **Gotowe**.
7.  W projektancie środowiska komórkowego na karcie **Pola** kliknij przycisk **Wybierz pola**. Kolumny na stronie listy muszą przypominać te na ilustracji poniżej. 

    [![Kolumny na stronie Oczekujące faktury od dostawcy — przypisane do mnie](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  Ze strony listy dodaj wymagane kolumny, które muszą być wyświetlane użytkownikom na stronie dla urządzeń komórkowych. Kolejność dodawania będzie kolejnością, w jakiej pola będą wyświetlane użytkownikowi końcowemu. Jedynym sposobem zmiany kolejności pól będzie ponowne wybranie wszystkich pól. Zgodnie z wymaganiami tego scenariusza wymaganych jest osiem poniższych pól. Jednak niektórzy użytkownicy mogą uznawać, że osiem pól to zbyt wiele informacji na urządzeniu przenośnym. W związku z tym w widoku listy dla urządzeń przenośnych przedstawimy tylko najważniejsze pola. Pozostałe pola będą wyświetlane w widoku szczegółów, który zaprojektujemy później. Na razie dodamy pola wymienione poniżej. Kliknij znak plusa (**+**) w tych kolumnach, aby dodać je do strony komórkowej.
    - Nazwa dostawcy
    - Suma faktury
    - Faktura akonto
    - Numer faktury
    - Data faktury

    Po dodaniu pól strona środowiska komórkowego musi przypominać ilustrację poniżej. 
    
    [![Strona po dodaniu pól](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  Należy także dodać następujące kolumny teraz, aby umożliwić obsługę akcji przepływu pracy później.
    - Pokaż zadanie ukończenia
    - Pokaż zadanie delegowania
    - Pokaż zadanie wycofania
    - Pokaż zadanie odrzucenia
    - Pokaż zadanie wnioskowania o wykonanie
    - Pokaż zadanie ponownego przesłania

10. Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.
11. Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.
12. Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.
13. W formularzu Parametry modułu rozrachunków z dostawcami w obszarze **Faktura** włącz opcję **Wyświetl sumę faktury na liście oczekujących faktur od dostawców** . Należy zauważyć, że tylko po włączeniu tego parametru będą obliczane sumy faktur z przeznaczeniem do wyświetlenia na stronie listy oczekujących faktur od dostawców. Jest to nowa funkcja zawarta w poprawce 3208224 stanowiącej wymóg wstępny.

### <a name="vendor-invoice-details"></a>Szczegóły faktur od dostawców

Aby zaprojektować stronę szczegółów faktur dla urządzeń przenośnych, użyj strony **VendMobileInvoiceHeaderDetails**. Należy zauważyć, że w zależności od liczby faktur istniejących w systemie ta strona pokazuje najstarszą fakturę (tzn. tę, która została utworzona jako pierwsza). Aby znaleźć konkretną fakturę, możesz użyć filtru z lewej strony. Jednak w tym przykładzie nie potrzebujemy konkretnej faktury. Potrzebujemy po prostu jakichś danych faktury, aby móc zaprojektować stronę dla urządzeń przenośnych. 

[![Strona przepływu pracy](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. W adresie URL zastąp nazwę elementu menu wyrażeniem **VendMobileInvoiceHeaderDetails**, aby otworzyć formularz.

2. Otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate).

3. Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.

4. Zaznacz utworzoną wcześniej stronę **Moje faktury od dostawców** i kliknij przycisk **Edytuj**.

5. Na karcie **Pola** kliknij nagłówek kolumny **Siatka**.

6. Kliknij kolejno opcje **Właściwości &gt; Dodaj stronę**. **Uwaga:** Po kliknięciu nagłówka **Siatka** i dodaniu strony automatycznie jest ustanawiana relacja ze stroną szczegółów.

7. Wprowadź tytuł strony, taki jak **Szczegóły faktury**, oraz opis, taki jak **Wyświetlanie nagłówka i szczegółów wiersza faktury**.

8. Kliknij przycisk **Wybierz pola**. Pamiętaj, że kolejność dodawania będzie kolejnością, w jakiej pola będą wyświetlane użytkownikowi końcowemu. Jedynym sposobem zmiany kolejności pól będzie ponowne wybranie wszystkich pól. 

9. Zgodnie z wymaganiami tego scenariusza dodaj następujące pola z nagłówka:
   - Nazwa dostawcy
   - Suma faktury
   - Faktura akonto
   - Numer faktury
   - Data faktury
   - Opis faktury
   - Termin
   - Waluta faktury

10. Dodaj następujące pola z siatki wierszy na stronie:
    - Kategoria zaopatrzenia
    - Ilość
    - Cena jednostkowa
    - Kwota netto wiersza
    - Wartość 1099

11. Po dodaniu wszystkich pól z dwóch poprzednich kroków kliknij przycisk **Gotowe**. Strona musi przypominać tę na ilustracji poniżej.
    
    [![Strona po dodaniu pól](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.

13. Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.

14. Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.

### <a name="workflow-actions"></a>Akcje przepływu pracy

Aby dodać akcje przepływu pracy użyj strony **VendMobileInvoiceHeaderDetails**. Aby otworzyć tę stronę, należy zastąpić nazwę elementu menu w adresie URL, tak jak poprzednio. Następnie otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate). Wykonaj następujące kroki, aby dodać akcje przepływu pracy na stronie szczegółów. Musisz mieć przypisane faktury będące w stanie umożliwiającym udostępnienie Ci akcji przepływu pracy, dla których zamierzasz projektować środowisko.

#### <a name="record-workflow-actions"></a>Rejestrowanie akcji przepływu pracy
1.  Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.
2.  Zaznacz utworzoną wcześniej stronę **Szczegóły faktury** i kliknij przycisk **Edytuj**.
3.  Na karcie **Akcje** kliknij przycisk **Dodaj akcję**.
4.  Wprowadź tytuł akcji, taki jak **Zatwierdź**, oraz opis, taki jak **Zatwierdź fakturę**. Należy zauważyć, że tytuł akcji wprowadzony w tym miejscu staje się nazwą akcji wyświetlaną użytkownikowi w aplikacji mobilnej.
5.  Kliknij przycisk **Gotowe**.
6.  Kliknij przycisk **Wybierz pola**.
7.  Przejdź przez proces przepływu pracy na stronie **VendMobileInvoiceHeaderDetails** i wykonaj akcję, która miała zostać nagrana. Pamiętaj, aby wprowadzić komentarz do przepływu pracy podczas tego procesu, tak aby pole komentarza również się znalazło w komórkowym środowisku obsługi.
8.  Po wykonaniu akcji przepływu pracy kliknij przycisk **Gotowe**, aby ukończyć zadanie Wybierz pola.
9.  Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.
10. Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.
11. Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.
12. Powtórz poprzednie kroki, aby zarejestrować wszystkie wymagane akcje przepływu pracy. 

#### <a name="create-a-js-file"></a>Tworzenie pliku .js
1. Otwórz aplikację Notatnik lub Microsoft Visual Studio i wklej poniższy kod źródłowy. Zapisz plik w formacie .js. Ten kod powoduje wykonanie następujących czynności:
    - Ukrywa dodatkowe kolumny dotyczące przepływu pracy, które wcześniej dodano na stronie listy elementów dla urządzeń przenośnych. Dodaliśmy te kolumny, tak aby aplikacja posiadała te informacje w kontekście i mogła wykonać następny krok.
    - Na podstawie aktywnego kroku przepływu pracy zastosuje logikę powodującą pokazanie tylko tych akcji.

    > [!NOTE]
    > Nazwy stron i innych formantów w kodzie źródłowym muszą być takie same, jak nazwy w obszarze roboczym.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```

2.  Przekaż plik kodu źródłowego do obszaru roboczego, wybierając kartę **Logika**.
3.  Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.
4.  Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.
5.  Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.

### <a name="vendor-invoice-attachments"></a>Załączniki faktur od dostawców

1. Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**.

2. Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.

3. Zaznacz utworzoną wcześniej stronę <strong>Szczegóły faktury** i kliknij przycisk **Edytuj</strong>.

4. Ustaw w opcji **Zarządzanie dokumentami** wartość **Tak**, jak pokazano poniżej. **Uwaga:** Jeśli nie ma żadnego wymogu wyświetlania załączników na urządzeniu przenośnym, można pozostawić tę opcję ustawioną na **Nie**, co jest ustawieniem domyślnym.
   
   ![Zarządzanie dokumentami](./media/docmanagement-216x300.png)

5. Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.

6. Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.

7. Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.

### <a name="vendor-invoice-line-distributions"></a>Dystrybucje wierszy faktury od dostawcy

Wymagania dotyczące tego scenariusza potwierdzają, że będzie tylko dystrybucja na poziomie wierszy, a fakturę zawsze będzie miała tylko jeden wiersz. Ponieważ ten scenariusz jest prosty, środowisko użytkownika na urządzeniu przenośnym również musi być na tyle proste, aby w celu wyświetlenia dystrybucji użytkownik nie musiał przechodzić kilka poziomów w głąb. Funkcjonalność faktur od dostawców obejmuje opcję wyświetlania wszystkich dystrybucji z nagłówka faktury. To zachowanie jest potrzebne w scenariuszu mobilnym. W związku z tym użyjemy strony **VendMobileInvoiceAllDistributionTree** do zaprojektowania tej części scenariusza mobilnego. 

> [!NOTE] 
> Znajomość wymagań pomaga nam zdecydować, której konkretnej strony należy użyć i jak dokładnie zoptymalizować komórkowe środowisko obsługi dla użytkownika podczas projektowania scenariusza. W drugim scenariuszu użyjemy innej strony do pokazania dystrybucji, ponieważ wymagania w tym scenariuszu się różnią.

1.  W adresie URL zastąp nazwę elementu menu tak jak poprzednio. Wyświetlona strona powinna przypominać tę na poniższej ilustracji.

    [![Strona wszystkich dystrybucji](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  Otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate).

3.  Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym. **Uwaga:** Zobaczysz, że dwie nowe strony zostały utworzone automatycznie. System tworzy te strony, ponieważ w poprzedniej sekcji włączone funkcję zarządzania dokumentami. Można zignorować te nowe strony.

4.  Kliknij przycisk **Dodaj stronę**.

5.  Wprowadź tytuł strony, taki jak **Widok księgowania**, oraz opis, taki jak **Widok księgowania faktury**.

6.  Kliknij przycisk **Gotowe**.

7.  Na karcie **Pola** kliknij przycisk **Wybierz pola**, zaznacz poniższe pola na stronie dystrybucji, a następnie kliknij przycisk **Gotowe**:
    1.  Ilość
    2.  Waluta
    3.  Konto księgowe

    > [!NOTE] 
    > Nie wybraliśmy kolumny **Opis** z siatki dystrybucji, ponieważ wymagania tego scenariusza potwierdziły, że cena rozszerzona jest jedną kwotą, dla której będą istniały dystrybucje. W związku z tym użytkownik nie będzie potrzebował dodatkowego pola w celu określenia typu kwoty, dla której jest określana dystrybucja. Jednak w następnym scenariuszu **użyjemy** tych informacji, ponieważ wymagania tego scenariusza określają, że dystrybucje istnieją również dla innych typów kwot (na przykład dla podatku).

8.  Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.

9.  Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.

10. Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.

#### <a name="adding-navigation-to-view-accounting-page"></a>Dodawanie nawigacji do strony „Wyświetlanie księgowania”

Strona środowiska komórkowego **Widok księgowania** nie jest obecnie połączona z żadną stroną mobilną, które do tej pory zaprojektowaliśmy. Ponieważ użytkownik powinien być w stanie przejść do strony **Widok księgowania** ze strony **Szczegóły faktury** na urządzeniu przenośnym, musimy zapewnić nawigację ze strony **Szczegóły faktury** do strony **Widok księgowania**. Ustanowimy tę nawigację przy użyciu dodatkowej logiki za pomocą kodu źródłowego JavaScript.

1.  Otwórz utworzony wcześniej plik .js i dodaj wiersze wyróżnione w poniższym kodzie źródłowym. Ten kod wykonuje dwa zadania:
    1.  Pomaga zagwarantować, że użytkownicy nie mogą przechodzić bezpośrednio z obszaru roboczego do strony **Widok księgowania**.
    2.  Ustanawia formant nawigacji ze strony **Szczegóły faktury** do strony **Widok księgowania**.

    > [!NOTE] 
    > Nazwy stron i innych formantów w kodzie źródłowym muszą być takie same, jak nazwy w obszarze roboczym.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```
    
2.  Przekaż plik kodu źródłowego do obszaru roboczego, wybierając kartę **Logika** w celu zastąpienia poprzedniego kodu.
3.  Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.
4.  Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.
5.  Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.

### <a name="validation"></a>Weryfikacja

Na urządzeniu przenośnym otwórz aplikację i połącz się z wystąpieniem. Koniecznie zaloguj się w firmie, gdzie faktury od dostawców są Ci przypisane do weryfikacji. Powinna być możliwość wykonania następujących czynności:

-   Wyświetlenie obszaru roboczego **Moje zatwierdzenia**.
-   Szczegółowe przejście do obszaru roboczego **Moje zatwierdzenia** i wyświetlenie strony **Moje faktury od dostawców**.
-   Szczegółowe przejście do strony **Moje faktury od dostawców** i wyświetlenie listy faktur, które są Ci przypisane.
-   Szczegółowe przejście do jednej z faktur i wyświetlenie szczegółów nagłówka oraz wierszy faktury.
-   Na stronie szczegółów wyświetlenie łącza do załączników oraz użycie tego łącza w celu przejścia do listy załączników i wyświetlenia załączników.
-   Na stronie szczegółów wyświetlenie łącza do strony **Widok księgowania** oraz użycie tego łącza w celu przejścia do strony dystrybucji i wyświetlenia dystrybucji.
-   Na stronie szczegółów u dołu kliknięcie menu **Akcje** i wykonanie akcji przepływu pracy mających zastosowanie do etapu przepływu pracy.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Projektowanie skomplikowanego scenariusza zatwierdzania faktur dla firmy Fabrikam
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
<td>Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</td>
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
<td>Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</td>
<td><ol>
<li>Kategoria zaopatrzenia</li>
<li>Ilość</li>
<li>Cena jednostkowa</li>
<li>Kwota netto wiersza</li>
<li>Wartość 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Ile wierszy faktury istnieje w fakturze? Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym?</td>
<td>Tak</td>
</tr>
<tr class="odd">
<td>Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty itd.) istnieje dla wiersza faktury? Tu również zastosuj regułę 80-20.</td>
<td>Cena rozszerzona: 2 Podatek: 2 Opłaty: 2</td>
</tr>
<tr class="even">
<td>Czy faktury mają również zasady podziału księgowań w nagłówku faktury? Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?</td>
<td>Nieużywane</td>
</tr>
<tr class="odd">
<td>Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?</td>
<td>Tak</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Następne kroki

W scenariuszu 1 można wprowadzić zmiany wymienione poniżej zgodnie z wymaganiami scenariusza 2. Informacje w tej sekcji pomogą usprawnić korzystanie z aplikacji komórkowej.

1.  Ponieważ w scenariuszu 2 jest potrzebnych więcej wierszy faktury, wymienione poniżej zmiany w projekcie pomogą zoptymalizować środowisko użytkownika na urządzeniu przenośnym:
    1.  Zamiast przeglądać wiersze faktury na stronie szczegółów (jak w scenariuszu 1), użytkownicy mogą wybrać opcję wyświetlania wierszy na osobnej stronie dla urządzeń komórkowych.
    2.  Ponieważ w tym scenariuszu jest potrzebny więcej niż jeden wiersz faktury, jeśli do projektowania strony dystrybucji dla urządzeń przenośnych jest używana strona **VendMobileInvoiceAllDistributionTree** (jak w scenariuszu 1), korelowanie wierszu z dystrybucjami może być mylące dla użytkownika. W związku z tym do projektowania strony dystrybucji użyj strony **VendMobileInvoiceLineDistributionTree**.
    3.  W idealnej sytuacji w tym scenariuszu dystrybucje powinny być pokazywane w kontekście wiersza faktury. W związku z tym upewnij się, że użytkownik może szczegółowo przejść do wiersza, aby zobaczyć stronę dystrybucji. Użyj funkcji łącza do strony, aby ustanowić drążenie wskroś, tak samo, jak to zrobiono dla stron nagłówka i szczegółów w scenariuszu 1.

2.  Ponieważ dystrybucje w scenariuszu 2 wymagają więcej niż jednego typu kwoty (podatek, opłaty i tak dalej), warto, aby były wyświetlane opisy typów kwot. (Pominęliśmy te informacje w scenariuszu 1).






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
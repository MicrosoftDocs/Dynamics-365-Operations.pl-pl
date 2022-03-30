---
title: Deklaracja VAT (Dania)
description: W tym temacie opisano, jak skonfigurować i wygenerować zaliczkową deklarację podatku od wartości dodanej (VAT) dla Danii.
author: anasyash
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4d4a1185fa3c3b059744018b6e4e195de07126c9
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2022
ms.locfileid: "8402987"
---
# <a name="vat-declaration-denmark"></a>Deklaracja VAT (Dania)

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak skonfigurować deklarację podatku od wartości dodanej (VAT) dla Danii i wyświetlić jej podgląd w Microsoft Excel.

Aby automatycznie wygenerować raport, należy najpierw utworzyć wystarczającą liczbę kodów podatków, aby zachować oddzielne księgowanie podatku VAT dla każdego pola w deklaracji zaliczki na podatek VAT. Ponadto w specyficznych dla aplikacji parametrach formatu raportowania elektronicznego (ER) dla deklaracji zaliczki na podatek VAT należy skojarzyć kody podatków z wynikami wyszukiwania pól w deklaracji podatku VAT.

Dla Danii należy skonfigurować **Wyszukiwanie pól raportu**. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów specyficznych dla aplikacji, zobacz sekcję [Konfigurowanie parametrów specyficznych dla aplikacji dla pól deklaracji podatku VAT](#set-up-application-specific-parameters) w dalszej części tego tematu.

W poniższej tabeli kolumna „Wynik wyszukiwania” zawiera wynik wyszukiwania, który jest wstępnie skonfigurowany dla określonego wiersza deklaracji podatku VAT w formacie deklaracji podatku VAT. Aby poprawnie skojarzyć kody podatków z wynikami wyszukiwania, a następnie z wierszem deklaracji podatku VAT, należy skorzystać z tych informacji.

### <a name="vat-declaration-overview"></a>Deklaracja podatku VAT — omówienie

Deklaracja VAT w Danii zawiera następujące informacje.

**VAT do zapłacenia**

| Opis                                                  | Podstawa opodatkowania/kwota podatku | Wynik wyszukiwania/Suma                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Należny podatek VAT                                                   | Kwota podatku          | **OutputVAT**</br> **DomesticVATUseTax** (również zgłoszony w polu „Naliczony podatek VAT”)                                                                                                                                                                                                                                                                       |
| Podatek VAT od towarów itp. Zakupione za granicą                           | Kwota podatku          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (również zgłoszony w polu „Naliczony podatek VAT”)</br>**PurchaseGoodsEU** (Podstawa podatku jest zgłaszana w polu A — nabycie towarów)</br>**PurchaseGoodsEUUseTax** ((Kwota podatku jest również zgłaszana w polu "VAT naliczony". Podstawa podatku jest zgłaszana w polu A — nabycie towarów)                   |
| Podatek VAT od usług zakupionych za granicą podlegających opłacie zwrotnej | Kwota podatku          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (również zgłoszony w polu „Naliczony podatek VAT”)</br>**PurchaseServicesEU** (Podstawa podatku jest zgłaszana w polu A — nabycie towarów.)</br>**PurchaseServicesEUUseTax** ((Kwota podatku jest również zgłaszana w polu "VAT naliczony". Podstawa podatku jest zgłaszana w polu A — nabycie usług.) |
| Suma rozrachunków                                                | Kwota podatku          | Suma z poprzednich trzech pól                                                                                                                                                                                                                                                                                                            |

**Potrącenia**

| Opis                                                                               | Podstawa opodatkowania/kwota podatku | Wynik wyszukiwania/Suma                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Naliczony podatek VAT                                                                                 | Kwota podatku          | **InputVAT**</br> **DomesticVATUseTax** (również zgłoszony w polu „należny podatek VAT”)</br>**PurchaseGoodsAbroadUseTax** (również zgłoszony w polu „VAT od towarów itp. Zakupione za granicą)</br>**PurchaseServicesAbroadUseTax** (również zgłoszony w polu „Podatek VAT od usług zakupionych za granicą z opłatą zwrotną”)</br>**PurchaseGoodsEUUseTax** (również zgłoszony w polu „VAT od towarów itp. Zakupione za granicą)</br> **PurchaseServicesEUUseTax** (również zgłoszony w polu „Podatek VAT od usług zakupionych za granicą z opłatą zwrotną”) |
| Opłata za olej i gaz w butlach                                                                  | Kwota podatku          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Opłata za emisję gazu ziemnego i miejskiego                                                             | Kwota podatku          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Opłata za emisję                                                                               | Kwota podatku          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Kwota podatku          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Opłata za wodę                                                                              | Kwota podatku          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Suma potrąceń                                                                          | Kwota podatku          | Suma z poprzednich sześciu pól                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Łączna kwota opłat (kwota dodatnia = dokonanie płatności, kwota ujemna = otrzymanie zwrotu) | Kwota podatku          | „Suma zobowiązań” – „Suma potrąceń”                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Informacje dodatkowe**

| Opis                                                                                                                                                                                                                                | Podstawa opodatkowania/kwota podatku | Wynik wyszukiwania/Suma                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Pole A — nabycie towarów. Wartość nabycia towarów przez związek bez podatku VAT.                                                                                                                                                   | Podstawa opodatkowania            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Pole A — nabywanie usług. Wartość bez VAT wewnątrzunijnego nabycia usług.                                                                                                                                             | Podstawa opodatkowania            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Pole B — dostawa towarów — do deklaracji „Sprzedaż do UE bez VAT"/DK VIES. Wartość bez VAT wewnątrzunijnej dostawy towarów                                                                                                           | Podstawa opodatkowania            | **SalesGoodsEU**                                |
| Pole B — dostawy – nie należy zgłaszać do „sprzedaży UE bez VAT”/DK VIES. Wartość niektórych dostaw wewnątrzunijnych bez podatku VAT, np. instalacja, instalacja, sprzedaż na odległość oraz nowe środki transportu dla osób nie opodatkowania. | Podstawa opodatkowania            | **SalesInstallationAssemblyEtcEU**              |
| Pole B — dostawa usług. Wartość bez VAT wewnątrzunijnego świadczenia usług, za które nabywca jest zobowiązany zapłacić VAT jako odwrotne obciążenie – należy również zgłosić do „sprzedaży bez VAT UE”/DK VIES.                          | Podstawa opodatkowania            | **SalesServicesEU**                             |
| Pole C — inne materiały. Wartość dostaw innych towarów i usług dostarczanych bez podatku VAT na terytorium Danii, do innych krajów członkowskich UE, do krajów trzecich lub obszarów trzecich.                                     | Podstawa opodatkowania            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>Opłata zwrotna VAT od zakupu

W przypadku skonfigurowania kodów podatków do przychodzącej opłaty zwrotnej VAT należy skojarzyć kody podatków z wynikami **Wyszukiwania pól raportu** zawierającym w nazwie podatek „UseTax”.

Można również skonfigurować dwa osobne kody podatków: jeden dla podatku VAT należnego i jeden dla potrącenia podatku VAT. Następnie skojarz każdy kod z odpowiednimi wynikami **Wyszukiwania pola raportu**.

Na przykład w przypadku opodatkowanych wewnątrzwspólnotowych transakcji nabycia należy skonfigurować kod podatku **UT_S_EU** z ewentualnym podatkiem obrotowym i skojarzyć go z wynikiem wyszukiwania **PurchaseGoodsEUUseTax** pola **Wyszukiwanie pól raportu**. W takim przypadku kwoty podatku używające kodu podatku od sprzedaży **UT_S_EU** są uwzględniane w „VAT od towarów itp. Pola „Podatek VAT od zakupu za granicą” i „Naliczony podatek VAT”. Podstawy opodatkowania są odzwierciedlone w „polu A - nabycie towarów”.

Można również skonfigurować dwa kody podatków:

- kod **VAT_S_EU**, którego wartość stawki podatku wynosi -25 procent
- kod **InVAT_S_EU**, którego wartość stawki podatku wynosi 25 procent

Następnie skojarz kody wyników wyszukiwania pola **Wyszukiwania pola raportu** w następujący sposób:

- Skojarz kod **VAT_S_EU** z wynikiem wyszukiwania **PurchaseGoodsEU**.
- Skojarz kod **InVAT_S_EU** z wynikiem wyszukiwania **InputVAT**.

W takim przypadku kwoty podatku używające kodu podatku od sprzedaży **VAT_S_EU** są uwzględniane w „VAT od towarów itp. zakupione za granicą" oraz pole "Pole A - nabycie towarów". Kwoty, które używają kody podatku **InVAT_S_EU** są odzwierciedlone w polu "VAT naliczony".

Aby uzyskać więcej informacji na temat konfigurowania opłaty zwrotnej VAT, zobacz temat [Opłaty zwrotne](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Konfigurowanie parametrów systemu

Aby wygenerować deklarację VAT, należy skonfigurować numer VAT.

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
2. Wybierz firmę i wybierz przycisk **Identyfikatory rejestracji**.
3. Wybierz lub utwórz adres w Danii, a następnie na skróconej karcie **Identyfikator rejestracji** wybierz opcję **Dodaj**.
4. W polu **Typ rejestracji** wybierz typ rejestracji przeznaczony dla Danii, który używa kategorii rejestracji **Identyfikator VAT**.
5. W polu **Numer rejestracji** wpisz numer podatku.
6. Na karcie **Ogólne** w polu **Data wprowadzenia** wprowadź datę, od kiedy zaczyna obowiązywać numer.

Aby uzyskać więcej informacji na temat konfigurowania kategorii rejestracji i typów rejestracji, przejrzyj [Identyfikatory rejestracji](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Skonfiguruj podgląd deklaracji VAT dla Danii

### <a name="import-er-configurations"></a>Importowanie konfiguracji ER

Otwórz obszar roboczy **Raportowanie elektroniczne** i zaimportuj format raportowania **elektronicznego (DK)** deklaracji VAT.

Więcej informacji można znaleźć w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Ustaw parametry specyficzne dla aplikacji dla pól deklaracji podatku VAT

> [!NOTE]
> Zaleca się włączenie tej funkcji: **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Gdy ta funkcja jest włączona, parametry skonfigurowane dla wcześniejszej wersji formatu raportowania elektronicznego automatycznie stają się dostępne dla nowszej wersji tego samego formatu. Jeśli ta funkcja nie jest włączona, należy skonfigurować parametry specyficzne dla aplikacji jawnie dla każdej wersji formatu. Funkcja **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** jest dostępna w obszarze roboczym **Zarządzanie funkcjami** w aplikacji Finance w wersji 10.0.23. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów formatu raportowania elektronicznego dla każdej firmy, zobacz temat [Konfigurowanie parametrów formatu raportowania elektronicznego według firmy](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Aby automatycznie wygenerować deklarację podatku VAT, należy skojarzyć kody podatków w aplikacji i wyniki wyszukiwania w konfiguracji raportowania elektronicznego.

Aby określić, które kody podatków generują pola deklaracji podatku VAT, należy wykonać następujące kroki.

1. Przejdź do opcji **Obszar roboczy** > **Raportowanie elektroniczne** i wybierz opcję **Konfiguracje raportowania**.
2. Wybierz konfigurację **Deklaracja podatku Excel (DK)**, a następnie wybierz **Konfiguracje \> Ustawianie parametrów specyficznych dla aplikacji**.
3. Na stronie **Parametry specyficzne dla aplikacji**, na skróconej karcie **Wyszukiwania** wybierz pozycję **Wyszukiwanie pól raportu**.
4. Na skróconej karcie **Warunki** ustaw następujące pola, aby skojarzyć kody podatków i pola raportu.

    | Pole                  | Opis                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Wynik wyszukiwania          | Wybierz wartość pola raportu. Aby uzyskać więcej informacji o wartościach i ich przypisywaniu do wierszy deklaracji podatku VAT, zobacz sekcję [Omówienie deklaracji VAT](#vat-declaration-overview) wcześniej w tym temacie.                                                                                               |
    | Kod podatku               | Wybierz kod podatku, z którym będzie skojarzony z polem raportu. W odpowiednim polu deklaracji zostaną zebrane zaksięgowane transakcje podatkowe o wybranym kodzie podatku. Zaleca się rozdzielanie kodów podatków w taki sposób, aby jeden kod podatku generował kwoty tylko w jednym polu deklaracji. |
    | Klasyfikator transakcji | W przypadku utworzenia wystarczającej liczby kodów podatków do ustalenia pola deklaracji, należy zaznaczyć pole **\*Niepuste\***. Jeśli utworzono za mało kodów podatków, aby jeden kod podatku generował kwoty tylko w jednym polu deklaracji, można skonfigurować klasyfikator transakcji. Dostępne są następujące klasyfikatory transakcji:</br>-   **Zakup**</br>-   **PurchaseExempt** (zakup zwolniony z podatku)</br>-   **PurchaseReverseCharge** (podatek naliczony z opłaty zwrotnej zakupu)</br>-   **Sprzedaż**</br>-   **SalesExempt** (sprzedaż zwolniona z podatku)</br>-   **SalesReverseCharge** (podatek należny z opłaty zwrotnej zakupu lub opłaty zwrotnej sprzedaży)</br>-   **Podatek obrotowy**. </br>Dla każdego klasyfikatora transakcji jest również dostępny klasyfikator dla faktury korygującej. Na przykład jednym z tych klasyfikatorów jest **PurchaseCreditNote** (faktura korygująca zakupu).</br>Dla każdego kodu podatku należy utworzyć dwa wiersze: jeden z wartością klasyfikatora transakcji oraz jeden z klasyfikatorem transakcji dla wartości faktury korygującej. |


    > [!NOTE]
    > Skojarz wszystkie kody podatków z wynikami wyszukiwania. Jeśli jakiekolwiek kody podatków nie powinny generować wartości w deklaracji podatku VAT, należy je skojarzyć z wynikami wyszukiwania **Inne**.

    ![Strona parametry specyficzne dla aplikacji.](media/7db74920fad66a0db7fad60758698cc0.png)


5. Zmień wartość w polu **Stan** na **Zakończono**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Konfigurowanie formatu raportowania podatku VAT dla podglądu kwot w programie Excel

1. W obszarze roboczym **Zarządzanie funkcjami** znajdź i włącz **Raportu formatu zestawienia podatku VAT**. na liście, a następnie wybierz **Wyłącz teraz**.
2. Przejdź do opcji **Księga główna** > **Ustawienia** > **Parametry księgi głównej**.
3. Na karcie **Podatek**, w skróconej karcie **Opcje podatku**, w polu **Mapowanie formatu deklaracji VAT** wybierz opcję **Deklaracja podatku VAT Excel (DK)**.

   Ten format jest drukowany po uruchomieniu raportu **Podatek raportu dla okresu rozliczeniowego**. Jest także drukowany po wybraniu opcji **Drukuj** na stronie **Płatności podatku**.

4. Na stronie **Urzędy skarbowe** wybierz urząd skarbowy, a następnie w polu **Układ raportu** wybierz pozycję **Domyślne**.

Jeśli konfigurujesz deklarację podatku VAT w osobie prawnej, która ma [wiele rejestracji podatku VAT](emea-reporting-for-multiple-vat-registrations.md), wykonaj następujące czynności.

1. Przejdź do pozycji **Księga główna** \> **Ustawienia** \> **Parametry księgi głównej**.
2. Na karcie **Podatek**, na skróconej karcie **Raportowanie elektroniczne dla krajów/regionów** w wierszu **DNK** wybierz format raportowania elektronicznego **Deklaracji podatkowej Excel (DK)**.

## <a name="set-up-electronic-messages"></a>Ustawianie wiadomości elektronicznych

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Pobierz i importuj pakiet danych, który zawiera przykładowe ustawienia wiadomości elektronicznych

Pakiet danych zawiera ustawienia wiadomości elektronicznych, które służą do podglądu deklaracji VAT w programie Excel. Można rozszerzyć te ustawienia lub utworzyć własne. Aby uzyskać więcej informacji na temat pracy z wiadomościami elektronicznymi i tworzenia własnych ustawień, zobacz [Wiadomości elektroniczne](../general-ledger/electronic-messaging.md).

1. W rozwiązaniu [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/v2) w bibliotece aktywów wspólnych wybierz **Pakiet danych** jako typ aktywów, a następnie pobierz **Pakiet wiadomości elektronicznych deklaracji podatku VAT DK**. Nazwa pobranego pliku to **Pakiet deklaracji VAT DK.zip**.
2. W rozwiązaniu Finance, w obszarze roboczym **Zarządzanie danymi** wybierz opcję **Importuj**.
3. Na skróconej karcie **Import** w polu **Nazwa grupy** wpisz nazwę dla zadania.
4. Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj plik**.
5. W oknie dialogowym **Dodaj plik** sprawdź, czy w polu **Format danych źródłowych** jest ustawiona wartość **Pakiet**, wybierz opcję **Przekaż i dodaj**, a następnie wybierz pobrany wcześniej plik ZIP.
6. Kliknij przycisk **Zamknij**.
7. Po przekazania jednostek danych wybierz przycisk **Importuj** w okienku akcji.
8. Przejdź do **Podatek** > **Zapytania i raporty** > **Wiadomości elektroniczne** > **Wiadomości elektroniczne** i sprawdź poprawność zaimportowanej przetwarzania wiadomości elektronicznej (**Deklaracja VAT DK**).

### <a name="configure-electronic-messages"></a>Konfiguruj wiadomości elektroniczne

1. Przejdź do **Podatek** > **Konfiguracja** > **Wiadomości elektroniczne** > **Wypełnij akcje rekordów**.
2. Zaznacz wiersz dla **Wypełnienia rekordów zwrotu podatku VAT DK**, a następnie wybierz polecenie **Edytuj zapytanie**.
3. Ten filtr umożliwia określenie okresów rozliczenia, które mają być uwzględniane w raporcie.
4. Jeśli musisz raportować transakcje podatkowe z innych okresów rozliczeniowych w innej deklaracji, utwórz nową akcję **Wypełnij rekordy** i wybierz odpowiednie okresy rozliczenia.

## <a name="preview-the-vat-declaration-in-excel"></a>Podgląd deklaracji podatku VAT w programie Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a>Podgląd deklaracji podatku VAT w programie Excel z zadania okresowego Raport podatkowy dla okresu rozliczeniowego

1. Wybierz kolejno opcje **Podatek** > **Zadania okresowe** > **Deklaracje** > **Podatek** > **Raportuj podatek dla okresu rozliczeniowego**.
2. W polu **Okres rozliczeniowy** wybierz wartość.
3. W polu **Wersja płatności podatku** wybierz jedną z następujących wartości:

    - **Oryginał**: generowanie raportu dla transakcji podatkowych oryginalnej płatności podatku lub przed wygenerowaniem płatności podatku.
    - **Korekty**: generowanie raportu dla transakcji podatkowych wszystkich kolejnych płatności podatku dla okresu.
    - **Lista sum**: generowanie raportu dla wszystkich transakcji podatkowych dla okresu, uwzględniając oryginały i korekty.

4. W polu **Od dnia** wybierz datę początkową okresu raportowania.
5. Wybierz przycisk **OK** i przejrzyj raport w programie Excel.

### <a name="settle-and-post-sales-tax"></a>Rozlicz i zaksięguj podatek

1. Wybierz kolejno opcje **Podatek** > **Zadania okresowe** > **Deklaracje** > **Podatek** > **Rozlicz i zaksięguj podatek**.
2. W polu **Okres rozliczeniowy** wybierz wartość.
3. W polu **Wersja płatności podatku** wybierz jedną z następujących wartości:

    - **Oryginał**: generowanie oryginalnej płatności podatku dla okresu rozliczeniowego.
    - **Ostatnie korekty**: generowanie płatności korekty podatku po utworzeniu oryginalnej płatności podatku dla okresu rozliczeniowego.

4. W polu **Od dnia** wybierz datę początkową okresu raportowania.
5. Kliknij przycisk **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Podgląd deklaracji podatku VAT w programie Excel z płatności podatku

1. Przejdź do opcji **Podatek** > **Zapytania i raporty** > **Zapytania dotyczące podatków** > **Płatności podatków** i wybierz wiersz płatności podatku.
2. Wybierz opcję **Drukuj raport**, a następnie wybierz opcję **OK**.
3. Przejrzyj plik programu Excel wygenerowany dla wybranego wiersza płatności podatku.

> [!NOTE]
> Raport jest generowany tylko dla wybranego wiersza płatności podatku. Aby na przykład wygenerować deklarację korekty zawierającą wszystkie korekty dla okresu lub deklarację zastępczą zawierającą oryginalne dane i wszystkie korekty, użyj zadania okresowego **Raport podatkowy dla okresu rozliczeniowego**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generowanie deklaracji podatku VAT z komunikatów elektronicznych

Gdy do generowania raportu są używane wiadomości elektroniczne, można zbierać dane podatkowe od wielu osób prawnych. Aby uzyskać więcej informacji, zobacz sekcję [Uruchamianie deklaracji podatku VAT dla wielu osób prawnych](#run-vat-declaration) w dalszej części tego tematu.

Następująca procedura jest stosowana w przykładzie przetwarzania wiadomości elektronicznych zaimportowanych z biblioteki udostępnionych wcześniej elementów zawartości usługi LCS.

1. Przejdź do menu **Podatek \> Zapytania i raporty \> Wiadomości elektroniczne \> Wiadomości elektroniczne**.
2. W lewym okienku wybierz opcję **Deklaracja podatku VAT DK**.
3. Na skróconej karcie **Wiadomości** wybierz pozycję **Nowa**, a następnie w oknie dialogowym **Uruchom przetwarzanie** wybierz przycisk **OK**.
4. Wybierz utworzony wiersz wiadomości, wprowadź opis, a następnie określ daty rozpoczęcia i zakończenia dla deklaracji.

   > [!NOTE]
   > Kroki od 5 do 7 są opcjonalne.

5. Opcjonalnie: na skróconej karcie **Wiadomości** wybierz pozycję **Zbierz dane**, a następnie wybierz przycisk **OK**. Płatności podatku wygenerowane wcześniej są dodawane do wiadomości. Więcej informacji znajduje się w sekcji [Rozliczanie i księgowanie podatku](#settle-and-post-sales-tax) we wcześniejszej części tego tematu. Jeśli ten krok zostanie pominięty, nadal będzie można wygenerować deklarację podatku VAT, korzystając z pola **Wersja deklaracji podatkowej** w oknie dialogowym **Deklaracja**.
6. Opcjonalnie: na skróconej karcie **Elementy wiadomości** przejrzyj płatności podatku przeniesione do przetworzenia. Domyślnie uwzględniane są wszystkie płatności podatku z wybranego okresu, które nie zostały uwzględnione w żadnej innej wiadomości tego samego przetwarzania.
7. Opcjonalnie: wybierz **Dokument oryginalny**, aby przejrzeć płatności podatków, lub opcję **Usuń**, aby wykluczyć płatności podatku z przetwarzania. Jeśli ten krok zostanie pominięty, nadal będzie można wygenerować deklarację podatku VAT, korzystając z pola **Wersja deklaracji podatkowej** w oknie dialogowym **Deklaracja**.
8. Na skróconej karcie **Wiadomości** wybierz **Aktualizuj stan**. W oknie dialogowym **Aktualizacja stanu** wybierz pozycję **Gotowe do wygenerowania**, a następnie wybierz przycisk **OK**. Sprawdź, czy stan wiadomości został zmieniony na **Gotowe do wygenerowania**.
9. Wybierz pozycję **Generuj raport**. Aby wyświetlić podgląd kwot deklaracji podatku VAT, w oknie dialogowym **Uruchamianie przetwarzania** wybierz opcję **Podgląd raportu**, a następnie przycisk **OK**.
10. W oknie dialogowym **Parametry raportowania elektronicznego** ustaw pola w sposób opisany w sekcji [Podgląd deklaracji VAT w programie Excel](#preview-vat-excel) w sekcji zadania okresowego Raport podatku dla okresu rozliczeniowego wcześniej w tym temacie, a następnie wybierz **przycisk OK**.
11. Wybierz przycisk **Załączniki** (symbol spinacza do papieru) w prawym górnym rogu strony, a następnie wybierz **Otwórz** , aby otworzyć plik. Przejrzyj kwoty w dokumencie Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Uruchomienie deklaracji podatku VAT dla wielu firm

Aby użyć formatów do zgłaszania deklaracji podatku VAT dla grupy osób prawnych, należy najpierw skonfigurować parametry specyficzne dla aplikacji formatów raportowania elektronicznego dla kodów podatków ze wszystkich wymaganych osób prawnych.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Konfigurowanie wiadomości elektronicznych w celu zbierania danych podatkowych od kilku firm

Aby skonfigurować wiadomości elektroniczne, które będą zbierać dane od wielu firm, należy wykonać następujące kroki.

1. Kliknij kolejno opcje **Obszary robocze** > **Zarządzanie funkcjami**.
2. Znajdź i wybierz z listy **Zapytania między firmami dla akcji wypełniania rekordów na liście**, a następnie wybierz opcję **Włącz teraz**.
3. Przejdź do **Podatek** > **Konfiguracja** > **Wiadomości elektroniczne** > **Wypełnij akcje rekordów**.
4. Na stronie akcji **Wypełnij akcje rekordów** zaznacz wiersz dla **Wypełnij rekordy zwrotu podatku VAT DK**.

   W siatce **Ustawienia źródeł danych** jest dostępne nowe pole **Firma**. W przypadku istniejących rekordów w tym polu jest wyświetlany identyfikator bieżącej osoby prawnej.

5. W siatce **Ustawienia źródeł danych** dodaj wiersz dla każdej dodatkowej osoby prawnej, która musi zostać uwzględniona w raportowaniu. Dla każdego nowego wiersza ustaw następujące pola.

    | Pole                  | Opis                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Nazwa                   | Wprowadź wartość, która pomoże w zrozumieniu, skąd pochodzi ten rekord. Na przykład wprowadź **Płatność podatku VAT od oddziału 1**. |
    | Typ elementu wiadomości      | Wybierz **Zwrot podatku VAT**. Jest to jedyna dostępna wartość dostępna dla wszystkich rekordów.                                    |
    | Typ konta           | Zaznacz **Wszystko**.                                                                                                               |
    | Nazwa tabeli głównej      | Określ wartość **TaxReportVoucher** dla wszystkich rekordów.                                                                             |
    | Pole numeru dokumentu  | Określ wartość **Załącznik** dla wszystkich rekordów.                                                                                      |
    | Pole daty dokumentu    | Określ wartość **TransDate** dla wszystkich rekordów.                                                                                    |
    | Pole konta dokumentu | Określ wartość **TaxPeriod** dla wszystkich rekordów.                                                                                    |
    | Firma                | Wybierz identyfikator osoby prawnej.                                                                                            |
    | Zapytanie użytkownika             | To pole wyboru jest zaznaczane automatycznie podczas definiowania kryteriów przez wybranie opcji **Edytuj zapytanie**.                                 |

6. Dla każdego nowego wiersza wybierz pozycję **Edytuj zapytanie** i określ okres rozliczenia dla osoby prawnej określonej w polu **Firma** w wierszu.

Po zakończeniu konfigurowania funkcja **Zbierz dane** na stronie **Wiadomości elektroniczne** zbiera płatności podatku od wszystkich zdefiniowanych osób prawnych.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

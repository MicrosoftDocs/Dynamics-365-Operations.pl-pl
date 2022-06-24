---
title: Deklaracja podatku VAT (Niemcy)
description: W tym artykule opisano sposób konfigurowania i generowania deklaracji podatku od towarów i usług (VAT) dla Niemiec w oficjalnym formacie XML.
author: anasyash
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: ff52963c03ec2eb662eb0c20ef2a960e3b999167
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879540"
---
# <a name="vat-declaration-germany"></a>Deklaracja podatku VAT (Niemcy)

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania i generowania deklaracji podatku od towarów i usług (VAT) dla Niemiec w oficjalnym formacie XML. W tym artykule opisano również sposób wyświetlania podglądu deklaracji VAT w programie Microsoft Excel.

Aby automatycznie wygenerować raport, należy utworzyć wystarczającą liczbę kodów podatków, aby zachować oddzielne księgowanie podatku VAT dla każdego pola w deklaracji zaliczki na podatek VAT. Ponadto w specyficznych dla aplikacji parametrach formatu raportowania elektronicznego (ER) dla deklaracji zaliczki na podatek VAT należy skojarzyć kody podatków z wynikami wyszukiwania pól w deklaracji podatku VAT.

Dla Niemiec należy skonfigurować **Wyszukiwanie pól raportu**. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów specyficznych dla aplikacji, zobacz sekcję [Konfigurowanie parametrów specyficznych dla aplikacji dla pól deklaracji podatku VAT](#set-up-application-specific-parameters-for-vat-declaration-fields) w dalszej części tego artykułu.

W poniższej tabeli kolumna „Wynik wyszukiwania” zawiera wynik wyszukiwania, który jest wstępnie skonfigurowany dla określonego wiersza deklaracji podatku VAT w formacie deklaracji podatku VAT. Aby poprawnie skojarzyć kody podatków z wynikami wyszukiwania, a następnie z wierszem deklaracji podatku VAT, należy skorzystać z tych informacji.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Deklaracja podatku VAT — omówienie

Deklaracja zaliczki na podatek VAT w Niemczech zawiera następujące informacje.

**SEKCJA — DOSTAWY I INNE USŁUGI**

**Sprzedaż opodatkowana**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                                                                                                                      | Wynik wyszukiwania                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Bez kodu     | Sprzedaż opodatkowana stawką 19 procent.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) — ze znakiem minus             |
| 21  | 86             | Bez kodu     | Sprzedaż opodatkowana stawką 7 procent.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) — ze znakiem minus               |
| 22  | 35             | 36               | Sprzedaż opodatkowana z innymi stawkami podatku.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) — ze znakiem minus      |
| 23  | 77             | *Bez kwoty podatku*  | Dostawy z firm rolniczych i leśnych zgodnie z niemiecką ustawą VAT, §24 (UStG) do odbiorców o numerach identyfikacyjnych podatku VAT. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) — ze znakiem minus |
| 24  | 76             | 80               | Sprzedaż, za która musi zostać zapłacony podatek, zgodnie z wytycznymi §24 UStG (wyroby tartaczne, napoje i płyny alkoholowe).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Sprzedaż wolna od podatku z odliczeniem podatku naliczonego**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                                                       | Wynik wyszukiwania                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Bez kwoty podatku*  | Dostawy wewnątrzwspólnotowe do odbiorców z identyfikatorem podatku VAT.                       | 26-EUSales                          |
| 27  | 44             | *Bez kwoty podatku*  | Wewnątrzwspólnotowe dostawy nowych pojazdów na nabywców, którzy nie mają identyfikatora podatku VAT.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Bez kwoty podatku*  | Wewnątrzwspólnotowe dostawy nowych pojazdów poza firmą.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Bez kwoty podatku*  | Inna sprzedaż nieopodatkowana z odliczeniem podatku naliczonego, taka jak dostawy eksportowe. | 29-ExportOtherTaxFreeSales          |

**Sprzedaż wolna od podatku bez odliczenia podatku naliczonego**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                            | Wynik wyszukiwania                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Bez kwoty podatku*  | Sprzedaż wolna od podatku, która nie ma potrącenia podatku naliczonego. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Nabycia wewnątrzwspólnotowe**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                                                                                                   | Wynik wyszukiwania                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Bez kwoty podatku*  | Wolne od podatku wewnątrzwspólnotowego nabycia niektórych przedmiotów i złota inwestycyjnego.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Bez kodu     | Opodatkowane wewnątrzwspólnotowe nabycia po stawce podatku wynoszącej 19 procent.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Bez kodu     | Opodatkowane wewnątrzwspólnotowe nabycia po stawce podatku wynoszącej 7 procent.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Opodatkowane wewnątrzwspólnotowe nabycia po innych stawkach podatku.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Podlegające opodatkowaniu wewnątrzwspólnotowe nabycia nowych pojazdów od dostawców, którzy nie mają numeru identyfikacji podatkowej VAT, po ogólnej stawce podatkowej. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SEKCJA — BENEFICJENT JAKO DŁUŻNIK PODATKOWY**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                                                        | Wynik wyszukiwania                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Inne usługi przedsiębiorstw oparte na pozostałej części obszaru Wspólnoty.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Sprzedaż zgodnie z art. 13b (2) nr 3 ustawy UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Inne usługi zgodnie z art. 13b (2) nr 1, 2 oraz 4 do 12 ustawy UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**SEKCJA — INFORMACJE DODATKOWE O SPRZEDAŻY**

| Wiersz | Pole — podstawa podatku  | Pole — kwota podatku | Opis                                                                                                | Wynik wyszukiwania                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Bez kwoty podatku*  | Dostawy dla pierwszego odbiorcy w przypadku transakcji trójstronnych wewnątrzwspólnotowych.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Bez kwoty podatku*  | Opodatkowana sprzedaż wykonującego przedsiębiorcy, za które odbiorca usługi jest winny podatek. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Bez kwoty podatku*  | Inne usługi niepodlegające opodatkowaniu.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Bez kwoty podatku*  | Inna sprzedaż nieopodatkowana, gdy miejsce wykonania nie jest w Niemczech.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Bez kwoty podatku* | *Bez kwoty podatku*  | VAT.                                                                                                       | Wiersz 20 + Wiersz 21 + Wiersz 22 + Wiersz 24 + Wiersz 34 + Wiersz 35 + Wiersz 36 + Wiersz 37 + Wiersz 40 + Wiersz 41 + Wiersz 42 |

**SEKCJA — PODLEGAJĄCY ODLICZENIU PODATEK NALICZONY**

| Wiersz | Pole — kwota podatku | Opis                                                                                                | Wynik wyszukiwania                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Kwoty podatku naliczonego od faktur z innych firm, usług i transakcji trójstronnych wewnątrzwspólnotowych.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) — ze znakiem minusa                                                                   |
| 56  | 61               | Kwoty podatku naliczonego z wewnątrzwspólnotowego nabycia towarów.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Poniesiony podatek importowy.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Kwoty podatku naliczonego od usług w rozumieniu sekcji §13b ustawy UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Kwoty podatku naliczonego obliczane według ogólnych średnich stawek.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) — ze znakiem minus                                                                                    |
| 60  | 59               | Potrącenie podatku naliczonego z dostaw wewnątrzwspólnotowych nowych pojazdów poza firmą i małymi firmami. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) — ze znakiem minus                                                                  |
| 61  | 64               | Korekta potrącenia podatku naliczonego.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | Pozostała kwota.                                                                                      | Wiersz 52 — wiersz 55 — wiersz 56 — wiersz 57 — wiersz 58 — wiersz 50 — wiersz 60 — wiersz 61                                                                                                        |

**SEKCJA — INNE KWOTY PODATKU**

| Wiersz | Pole — kwota podatku | Opis                                                                                                                                                                                                                                                         | Wynik wyszukiwania                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Podatek z powodu zmiany formy opodatkowania i dodatkowego podatku od płatności z tytułu przedpłat podatkowych z powodu zmiany stawki podatku.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Niepoprawne lub nieprawidłowo przedstawione kwoty podatku, które są widoczne na fakturach, oraz kwoty podatku należne zgodnie z art. 6a (4) zdanie 2, art. 17 (1) zdanie 7, art. 25b (2) ustawy UStG lub które są należne przez firmę outsourcingową lub magazyniera. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Potrącenie stałej specjalnej płatności zaliczki dla stałego rozszerzenia. Ten wiersz jest zazwyczaj wypełniany tylko ostatnim powiadomieniem o zaliczce okresu podatkowego.                                                                                                  | Parametr danych wejściowych użytkownika w oknie dialogowym raportu |
| 68  | 83               | Pozostała płatność zaliczki na podatek i pozostała nadwyżka. Uwzględnij znak minusa przed kwotą.                                                                                                                                                          | Wiersz 62 + wiersz 64 — wiersz 65 — wiersz 66             |

**SEKCJA — INFORMACJE DODATKOWE O REDUKCJACH**

| Wiersz | Pole — podstawa podatku | Pole — kwota podatku | Opis                                                            | Wynik wyszukiwania                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Zmniejszenie podstawy podatku w wierszach 20–24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Zmniejszenie kwot odliczalnego podatku naliczonego w wierszach 55, 59 i 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>Opłata zwrotna VAT od zakupu

W przypadku skonfigurowania kodów podatków do przychodzącej opłaty zwrotnej VAT należy skojarzyć kody podatków z wynikami **Wyszukiwania pól raportu** zawierającym w nazwie podatek „UseTax”.

Można również skonfigurować dwa osobne kody podatków: jeden dla podatku VAT należnego i jeden dla potrącenia podatku VAT. Następnie skojarz każdy kod z odpowiednimi wynikami **Wyszukiwania pola raportu**.

Na przykład w przypadku opodatkowanych wewnątrzwspólnotowych transakcji nabycia po standardowej stawce należy skonfigurować kod podatku **UT_S_EU** z ewentualnym podatkiem obrotowym i skojarzyć go z wynikiem wyszukiwania **34-UseTaxEUPurchaseStandard** pola **Wyszukiwanie pól raportu**. W takim przypadku kwoty, które używają kody podatku **UT_S_EU** są odzwierciedlane w polach 089 i 061 (wiersze 34 i 56).

Można również skonfigurować dwa kody podatków:

  - kod **VAT_S_EU**, którego wartość stawki podatku wynosi -19 procent
  - kod **InVAT_S_EU**, którego wartość stawki podatku wynosi 19 procent

Następnie skojarz kody wyników wyszukiwania pola **Wyszukiwania pola raportu** w następujący sposób:

  - Skojarz kod **VAT_S_EU** z wynikiem wyszukiwania **34-EUPurchaseStandard**.
  - Skojarz kod **InVAT_S_EU** z wynikiem wyszukiwania **56-InputTaxEUPurchase**.

W takim przypadku kwoty, które używają kody podatku **VAT_S_EU** są odzwierciedlane w polu 089 (wiersz 34). Kwoty, które używają kody podatku **InVAT_S_EU** są odzwierciedlane w polu 061 (wiersz 56).

Aby uzyskać więcej informacji na temat konfigurowania opłaty zwrotnej VAT, zobacz temat [Opłaty zwrotne](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Konfigurowanie parametrów systemu

Aby wygenerować deklarację podatku VAT, należy skonfigurować numer podatku (Steuernummer) organizacji.

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
2. Wybierz firmę i wybierz przycisk **Identyfikatory rejestracji**.
3. Wybierz lub utwórz adres w Niemczech, a następnie na skróconej karcie **Identyfikator rejestracji** wybierz opcję **Dodaj**.
4. W polu **Typ rejestracji** wybierz typ rejestracji przeznaczony dla Niemiec, który używa kategorii rejestracji **Identyfikator przedsiębiorstwa (COID)**.
5. W polu **Numer rejestracji** wpisz numer podatku.
6. Na karcie **Ogólne** w polu **Data wprowadzenia** wprowadź datę, od kiedy zaczyna obowiązywać numer.

Aby uzyskać więcej informacji na temat konfigurowania kategorii rejestracji i typów rejestracji, przejrzyj [Identyfikatory rejestracji](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Konfiguracja deklaracji podatku VAT dla Niemiec

### <a name="import-er-configurations"></a>Importowanie konfiguracji ER

Otwórz obszar roboczy **Raportowanie elektroniczne** i zaimportuj następujące wersje lub nowsze formaty raportowania elektronicznego:

   - Deklaracja podatku VAT Excel (DE).version.101.16.12.xml
   - Deklaracja podatku VAT XML (DE).version.101.16.12.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Ustaw parametry specyficzne dla aplikacji dla pól deklaracji podatku VAT

Aby automatycznie wygenerować deklarację podatku VAT, należy skojarzyć kody podatków w aplikacji i wyniki wyszukiwania w konfiguracji raportowania elektronicznego.

> [!NOTE]
> Zaleca się włączenie tej funkcji: **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Gdy ta funkcja jest włączona, parametry skonfigurowane dla wcześniejszej wersji formatu raportowania elektronicznego automatycznie stają się dostępne dla nowszej wersji tego samego formatu. Jeśli ta funkcja nie jest włączona, należy skonfigurować parametry specyficzne dla aplikacji jawnie dla każdej wersji formatu. Funkcja **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** jest dostępna w obszarze roboczym **Zarządzanie funkcjami** w aplikacji Finance w wersji 10.0.23. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów formatu raportowania elektronicznego dla każdej firmy, zobacz temat [Konfigurowanie parametrów formatu raportowania elektronicznego według firmy](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Aby określić, które kody podatków generują pola deklaracji podatku VAT, należy wykonać następujące kroki.

1. Przejdź do opcji **Obszar roboczy** > **Raportowanie elektroniczne** i wybierz opcję **Konfiguracje raportowania**.
2. Wybierz konfigurację **Deklaracja podatku VAT (DE)**, a następnie wybierz **Konfiguracje \> Ustawianie parametrów specyficznych dla aplikacji**.
3. Na stronie **Parametry specyficzne dla aplikacji**, na skróconej karcie **Wyszukiwania** wybierz pozycję **Wyszukiwanie pól raportu**.
4. Na skróconej karcie **Warunki** ustaw następujące pola, aby skojarzyć kody podatków i pola raportu.

    | Pole                  | Opis                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Wynik wyszukiwania          | Wybierz wartość pola raportu. Aby uzyskać więcej informacji o wartościach i ich przypisywaniu do wierszy deklaracji podatku VAT, zobacz sekcję [Omówienie deklaracji VAT](#vat-declaration-overview) wcześniej w tym artykule.                                                                                               |
    | Kod podatku               | Wybierz kod podatku, z którym będzie skojarzony z polem raportu. W odpowiednim polu deklaracji zostaną zebrane zaksięgowane transakcje podatkowe o wybranym kodzie podatku. Zaleca się rozdzielanie kodów podatków w taki sposób, aby jeden kod podatku generował kwoty tylko w jednym polu deklaracji. |
    | Klasyfikator transakcji | W przypadku utworzenia wystarczającej liczby kodów podatków do ustalenia pola deklaracji, należy zaznaczyć pole **\*Niepuste\***. Jeśli utworzono za mało kodów podatków, aby jeden kod podatku generował kwoty tylko w jednym polu deklaracji, można skonfigurować klasyfikator transakcji. Dostępne są następujące klasyfikatory transakcji:</br>-   **Zakup**</br>-   **PurchaseExempt** (zakup zwolniony z podatku)</br>-   **PurchaseReverseCharge** (podatek naliczony z opłaty zwrotnej zakupu)</br>-   **Sprzedaż**</br>-   **SalesExempt** (sprzedaż zwolniona z podatku)</br>-   **SalesReverseCharge** (podatek należny z opłaty zwrotnej zakupu lub opłaty zwrotnej sprzedaży)</br>-   **Podatek obrotowy**. </br>Dla każdego klasyfikatora transakcji jest również dostępny klasyfikator dla faktury korygującej. Na przykład jednym z tych klasyfikatorów jest **PurchaseCreditNote** (faktura korygująca zakupu).</br>Dla każdego kodu podatku należy utworzyć dwa wiersze: jeden z wartością klasyfikatora transakcji oraz jeden z klasyfikatorem transakcji dla wartości faktury korygującej. |

    > [!NOTE]
    > Skojarz wszystkie kody podatków z wynikami wyszukiwania. Jeśli jakiekolwiek kody podatków nie powinny generować wartości w deklaracji podatku VAT, należy je skojarzyć z wynikami wyszukiwania **Inne**.

    ![Strona parametry specyficzne dla aplikacji](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. Zmień wartość w polu **Stan** na **Zakończono**.
6. W okienku akcji wybierz opcję **Eksportuj**, aby wyeksportować ustawienia parametrów specyficznych dla aplikacji.
7. Wybierz konfigurację **Deklaracji VAT dla programu Excel (DE)**, a następnie w okienku akcji wybierz opcję **Importuj**, aby zaimportować parametry skonfigurowane dla **Deklaracji podatku VAT XML (DE)**.
8. W polu **Stan** wybierz opcję **ukończone**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Konfigurowanie formatu raportowania podatku VAT dla podglądu kwot w programie Excel

1. W obszarze roboczym **Zarządzanie funkcjami** znajdź i włącz funkcję **Raportu formatu zestawienia podatku VAT**.
2. Przejdź do opcji **Księga główna** > **Ustawienia** > **Parametry księgi głównej**.
3. Na karcie **Podatek**, w skróconej karcie **Opcje podatku**, w polu **Mapowanie formatu deklaracji VAT** wybierz opcję **Deklaracja podatku VAT Excel (DE)**.

   Ten format jest drukowany po uruchomieniu raportu **Podatek raportu dla okresu rozliczeniowego**. Jest także drukowany po wybraniu opcji **Drukuj** na stronie **Płatności podatku**.

4. Na stronie **Urzędy skarbowe** wybierz urząd skarbowy, a następnie w polu **Układ raportu** wybierz pozycję **Domyślne**.

Jeśli konfigurujesz deklarację podatku VAT w osobie prawnej, która ma [wiele rejestracji podatku VAT](emea-reporting-for-multiple-vat-registrations.md), wykonaj następujące czynności:

1. Przejdź do opcji **Księga główna** > **Ustawienia** > **Parametry księgi głównej**.
2. Na karcie **Podatek**, na skróconej karcie **Raportowanie elektroniczne dla krajów/regionów** w wierszu **DEU** wybierz format raportowania elektronicznego **Deklaracji podatkowej Excel (DE)**.

## <a name="set-up-electronic-messages"></a>Ustawianie wiadomości elektronicznych

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Pobierz i importuj pakiet danych, który zawiera przykładowe ustawienia wiadomości elektronicznych

Pakiet danych zawiera ustawienia wiadomości elektronicznych, które służą do generowania deklaracji podatku VAT w formacie XML, a następnie wyświetlania jej podglądu w programie Excel. Można rozszerzyć te ustawienia lub utworzyć własne. Aby uzyskać więcej informacji na temat pracy z wiadomościami elektronicznymi i tworzenia własnych ustawień, zobacz [Wiadomości elektroniczne](../general-ledger/electronic-messaging.md).

1. W rozwiązaniu [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/v2) w bibliotece aktywów wspólnych wybierz **Pakiet danych** jako typ aktywów, a następnie pobierz **Pakiet wiadomości elektronicznych deklaracji podatku VAT DE**. Nazwa pobranego pliku to **Pakiet wiadomości elektronicznych deklaracji podatku VAT DE.zip**.
2. W aplikacji Dynamics 365 Finance, w obszarze roboczym **Zarządzanie danymi** wybierz opcję **Importuj**.
3. Na skróconej karcie **Import** w polu **Nazwa grupy** wpisz nazwę dla zadania.
4. Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj plik**.
5. W oknie dialogowym **Dodaj plik** sprawdź, czy w polu **Format danych źródłowych** jest ustawiona wartość **Pakiet**, wybierz opcję **Przekaż i dodaj**, a następnie wybierz pobrany wcześniej plik ZIP.
6. Kliknij przycisk **Zamknij**.
7. Po przekazania jednostek danych wybierz przycisk **Importuj** w okienku akcji.
8. Przejdź do **Podatek** > **Zapytania i raporty** > **Wiadomości elektroniczne** > **Wiadomości elektroniczne** i sprawdź poprawność zaimportowanej przetwarzania wiadomości elektronicznej.

### <a name="configure-electronic-messages"></a>Konfiguruj wiadomości elektroniczne

1. Przejdź do **Podatek** > **Konfiguracja** > **Wiadomości elektroniczne** > **Wypełnij akcje rekordów**.
2. Zaznacz wiersz dla **Wypełnienia rekordów zwrotu podatku VAT DE**, a następnie wybierz polecenie **Edytuj zapytanie**.
3. Ten filtr umożliwia określenie okresów rozliczenia, które mają być uwzględniane w raporcie.
4. Jeśli musisz raportować transakcje podatkowe z innych okresów rozliczeniowych w innej deklaracji, utwórz nową akcję **Wypełnij rekordy** i wybierz odpowiednie okresy rozliczenia.

## <a name="preview-the-vat-declaration-in-excel"></a>Podgląd deklaracji podatku VAT w programie Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Podgląd deklaracji podatku VAT w programie Excel z zadania okresowego Raport podatkowy dla okresu rozliczeniowego

1. Wybierz kolejno opcje **Podatek** > **Zadania okresowe** > **Deklaracje** > **Podatek** > **Raportuj podatek dla okresu rozliczeniowego**.
2. W polu **Okres rozliczeniowy** wybierz wartość.
3. W polu **Wersja płatności podatku** wybierz jedną z następujących wartości:

    - **Oryginał**: generowanie raportu dla transakcji podatkowych oryginalnej płatności podatku lub przed wygenerowaniem płatności podatku.
    - **Korekty**: generowanie raportu dla transakcji podatkowych wszystkich kolejnych płatności podatku dla okresu.
    - **Lista sum**: generowanie raportu dla wszystkich transakcji podatkowych dla okresu, uwzględniając oryginały i korekty.

4. W polu **Od dnia** wybierz datę początkową okresu raportowania.
5. Wybierz przycisk **OK** i przejrzyj raport w programie Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Rozlicz i zaksięguj podatek

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

Gdy do generowania raportu są używane wiadomości elektroniczne, można zbierać dane podatkowe od wielu osób prawnych. Aby uzyskać więcej informacji, zobacz sekcję [Uruchamianie deklaracji podatku VAT dla wielu osób prawnych](#run-a-vat-declaration-for-multiple-legal-entities) w dalszej części tego artykułu.

Następująca procedura jest stosowana w przykładzie przetwarzania wiadomości elektronicznych zaimportowanych z biblioteki udostępnionych elementów zawartości usługi LCS.

1. Przejdź do menu **Podatek** > **Zapytania i raporty** > **Wiadomości elektroniczne** > **Wiadomości elektroniczne**.
2. W lewym okienku wybierz opcję **Deklaracja podatku VAT DE**.
3. Na skróconej karcie **Wiadomości** wybierz pozycję **Nowa**, a następnie w oknie dialogowym **Uruchom przetwarzanie** wybierz przycisk **OK**.
4. Wybierz utworzony wiersz wiadomości, wprowadź opis, a następnie określ daty rozpoczęcia i zakończenia dla deklaracji.

    > [!NOTE]
    > Kroki od 5 do 7 są opcjonalne.

5. Opcjonalnie: na skróconej karcie **Wiadomości** wybierz pozycję **Zbierz dane**, a następnie wybierz przycisk **OK**. Płatności podatku wygenerowane wcześniej są dodawane do wiadomości. Więcej informacji znajduje się w sekcji [Rozliczanie i księgowanie podatku](#settle-and-post-sales-tax) we wcześniejszej części tego artykułu. Jeśli ten krok zostanie pominięty, nadal będzie można wygenerować deklarację podatku VAT, korzystając z pola **Wersja deklaracji podatkowej** w oknie dialogowym **Deklaracja**.
6. Opcjonalnie: na skróconej karcie **Elementy wiadomości** przejrzyj płatności podatku przeniesione do przetworzenia. Domyślnie uwzględniane są wszystkie płatności podatku z wybranego okresu, które nie zostały uwzględnione w żadnej innej wiadomości tego samego przetwarzania.
7. Opcjonalnie: wybierz **Dokument oryginalny**, aby przejrzeć płatności podatków, lub opcję **Usuń**, aby wykluczyć płatności podatku z przetwarzania. Jeśli ten krok zostanie pominięty, nadal będzie można wygenerować deklarację podatku VAT, korzystając z pola **Wersja deklaracji podatkowej** w oknie dialogowym **Deklaracja**.
8. Na skróconej karcie **Wiadomości** wybierz **Aktualizuj stan**. W oknie dialogowym **Aktualizacja stanu** wybierz pozycję **Gotowe do wygenerowania**, a następnie wybierz przycisk **OK**. Sprawdź, czy stan wiadomości został zmieniony na **Gotowe do wygenerowania**.
9. Wybierz pozycję **Generuj raport**. Aby wyświetlić podgląd kwot deklaracji podatku VAT, w oknie dialogowym **Uruchamianie przetwarzania** wybierz opcję **Podgląd raportu**, a następnie przycisk **OK**.
10. W oknie dialogowym **Parametry raportowania elektronicznego** ustaw następujące pola, a następnie wybierz przycisk **OK**.

    | **Field**                                   | **opis**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Okres rozliczeniowy                           | Wybierz okres rozliczeniowy. Jeśli w kroku 5 wybrano opcję **Zbieranie danych**, to pole można pozostawić puste. Raport zostanie wygenerowany dla transakcji podatkowych uwzględnionych w płatnościach podatku zebranego. |
    | Wersja deklaracji podatkowej                     | Należy wybrać jedną z następujących opcji:</br>-   **Oryginał** — generowanie raportu dla transakcji podatkowych oryginalnej płatności podatku lub przed wygenerowaniem płatności podatku.</br>-   **Korekty** — generowanie raportu dla transakcji podatkowych wszystkich kolejnych płatności podatku dla okresu.</br>-   **Lista sum** — generowanie raportu dla wszystkich transakcji podatkowych dla okresu, uwzględniając oryginały i korekty.|
    | Przedstawiciel podatkowy | Umożliwia wybór strony, która jest przedstawicielem podatkowym dla deklaracji podatku VAT, jeśli ma zastosowanie. Informacje o wybranej stronie są eksportowane do elementu XML **DatenLieferant**. |
    | Osoba kontaktowa | Umożliwia wybór osoby w organizacji, która jest dostawcą danych. Informacje o wybranej osobie są eksportowane do elementu XML **DatenLieferant**. |
    | Korekcyjny zwrot | Wybierz opcję **Tak**, jeśli jest to korekta deklaracji podatku VAT. W tym przypadku element XML KZ10 będzie miał wartość **1**.|
    | Dokumenty pomocnicze | Wybierz przycisk **Tak**, jeśli wysyłasz również dokumenty pomocy technicznej. W tym przypadku element XML KZ22 będzie miał wartość **1**.|
    | Upoważnienie bankowe dla polecenia zapłaty SEPA zostanie wycofane jako wyjątek| Wybierz opcję **Tak**, jeśli upoważnienie do polecenia zapłaty SEPA zostanie anulowane jako wyjątek dla tego okresu wstępnej rejestracji. Na przykład z powodu przeciwstawiania żądań. Pozostałe saldo należy spłacić oddzielnie. W tym przypadku element XML KZ26 będzie miał wartość **1**. |
    | Kompensowanie żądanej kwoty zwrotu | Wybierz opcję **Tak**, jeśli żądana przeciwstawna kwota zwrotu lub kwota zwrotu została przypisana. W tym przypadku element XML KZ29 będzie miał wartość **1**. |
    | Stałe rozszerzenie płatności zaliczki specjalnej | Wprowadź kwotę potrącenia stałej specjalnej płatności zaliczki dla stałego rozszerzenia. Ta kwota potrącenia zazwyczaj jest wypełniana tylko w ostatniej wstępnej rejestracji okresu podatkowego. Kwota zostanie wyeksportowana w wierszu 67 (pole 39) i elemencie XML KZ39 deklaracji podatku VAT. |

11. Wybierz opcję **Załączniki** znajdującą się w prawym górnym rogu strony, a następnie wybierz opcję **Otwórz**.
12. Przejrzyj kwoty w dokumencie programu Excel, a następnie wybierz pozycję **Generuj raport**.
13. Aby wygenerować deklarację podatku VAT w formacie XML, w oknie dialogowym **Uruchamianie przetwarzania** wybierz opcję **Generuj raport**, a następnie przycisk **OK**.
14. W oknie dialogowym **Parametry raportowania elektronicznego** ustaw pola w sposób opisany w kroku 10.
15. Wybierz opcję **Załączniki** w prawym górnym rogu strony, pobierz plik i użyj go do przesłania do urzędu skarbowego.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Uruchomienie deklaracji podatku VAT dla wielu firm

Aby użyć formatów do zgłaszania deklaracji podatku VAT dla grupy osób prawnych, należy najpierw skonfigurować parametry specyficzne dla aplikacji formatów raportowania elektronicznego dla kodów podatków ze wszystkich wymaganych osób prawnych.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Konfigurowanie wiadomości elektronicznych w celu zbierania danych podatkowych od kilku firm

Aby skonfigurować wiadomości elektroniczne, które będą zbierać dane od wielu firm, należy wykonać następujące kroki.

1. Kliknij kolejno opcje **Obszary robocze** > **Zarządzanie funkcjami**.
2. Znajdź i wybierz z listy **Zapytania między firmami dla akcji wypełniania rekordów na liście**, a następnie wybierz opcję **Włącz teraz**.
3. Przejdź do **Podatek** > **Konfiguracja** > **Wiadomości elektroniczne \> Wypełnij akcje rekordów**.
4. Na stronie akcji **Wypełnij akcje rekordów** zaznacz wiersz dla **Wypełnij rekordy zwrotu podatku VAT DE**.

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

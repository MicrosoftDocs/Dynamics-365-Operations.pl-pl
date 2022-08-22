---
title: Deklaracja podatku VAT dla Egiptu
description: W tym artykule opisano sposób konfigurowania i generowania formularza zwrotu podatku VAT dla Egiptu.
author: AdamTrukawka
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.search.scope: ''
ms.openlocfilehash: c035c52d7d577a01f5903461548c0cb33f05045f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287830"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Deklaracja VAT dla Egiptu (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

W tym artykule opisano sposób skonfigurowania i wygenerowania formularza zwrotu podatku VAT oraz ksiąg sprzedaży i zakupów dla firm w Egipcie.

Formularz deklaracji VAT dla Egiptu jest oficjalnym dokumentem, który podsumowuje całkowitą należną kwotę podatku VAT, łączną kwotę podatku naliczonego VAT do odzyskania i związaną z tym kwotę podatku VAT. Ten formularz jest używany dla wszystkich typów podatników i należy go wypełnić ręcznie za pośrednictwem portalu urzędu skarbowego. Formularz zwrotu podatku VAT jest zazwyczaj nazywany składaniem deklaracji zwrotu podatku VAT.

Formularz zwrotu podatku VAT w aplikacji Dynamics 365 Finance zawiera następujące raporty:

- Formularz deklaracji VAT nr 10, który zawiera zestawienie kwot, korekt i kwoty VAT według pozycji w formularzu deklaracji VAT, zgodnie z opisem w przepisach.
- Księga transakcji sprzedaży
- Księga transakcji zakupu

## <a name="prerequisites"></a>Wymagania wstępne
Podstawowy adres firmy musi być w Egipcie.
W obszarze roboczym **Zarządzanie funkcjami** włącz następujące funkcje:

   - (Egipt) Hierarchia kategorii dla raportu podatku od sprzedaży i zakupu.

Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

W obszarze roboczym **Raportowanie elektroniczne** zaimportuj następujący format raportowania elektronicznego z repozytorium:

- Deklaracja VAT Excel (EG)

> [!NOTE]
> Powyższy format jest oparty na **Modelu deklaracji podatkowej** i korzysta z **Mapowania modelu deklaracji podatkowej**. Dodatkowe konfiguracje zostaną zaimportowane automatycznie.

Aby uzyskać więcej informacji dotyczących importowania konfiguracji raportowania elektronicznego, zobacz temat [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Pobieranie konfiguracji raportowania elektronicznego

Implementacja formularza zwrotu VAT dla Egiptu jest oparta na konfiguracjach raportowania elektronicznego (RE). Aby uzyskać więcej informacji o możliwościach i pojęciach dotyczących raportowania konfigurowalnego, zobacz temat [Raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Aby uzyskać informacje o środowiskach testowania akceptacji użytkowników i produkcji (UAT), zobacz temat [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Aby wygenerować formularz zwrotu VAT i powiązane raporty w firmie Egipt, przekaż następujące konfiguracje:

- Wersja pliku model.version.70.xml lub jego nowsza wersja
- Wersja pliku mapping.version.70.120.xml lub jego nowsza wersja
- Deklaracja VAT Excel (EG).version.70.32 lub nowsza wersja

Po pobraniu konfiguracji ER z usługi Lifecycle Services (LCS) lub repozytorium globalnego wykonaj następujące kroki.

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.
1. Na stronie **Konfiguracje**, w okienku akcji wybierz **Import/eksport** > **Załaduj z pliku XML**.
1. Przekaż pliki w kolejności, w jakiej są wymienione powyżej. Po przekazaniu wszystkich konfiguracji drzewo konfiguracji powinno być obecne w Finance.

## <a name="set-up-application-specific-parameters"></a>Konfigurowanie parametrów specyficznych dla aplikacji

Parametry specyficzne dla aplikacji pozwalają określić kryteria klasyfikowania i obliczania transakcji podatkowych w każdym wierszu podczas generowania raportu. Ustalenie jest oparte na konfiguracji grupy podatków dla towaru, grupy podatków, kodu podatku i innych kryteriów ustalonych w definicji wyszukiwania.

Raporty księgi sprzedaży i zakupu dla Egiptu zawierają zestaw kolumn, które odpowiadają określonym klasyfikacjom transakcji jako typom operacji, produktów i dokumentów specyficznych dla Egiptu. Zamiast ująć te nowe klasyfikacje jako nowe dane wprowadzania podczas księgowania transakcji, klasyfikacje będą ustalane na podstawie różnych wyszukiwania wprowadzonych w **Konfiguracje** > **Konfigurowanie parametrów specyficznych dla aplikacji** > **Konfiguracja**, aby spełnić wymagania zgłaszania VAT w Egipcie. 

![Strona parametry specyficzne dla aplikacji.](media/egypt-vat-declaration-setup1.png)

Następujące konfiguracje wyszukiwania służą do klasyfikowania transakcji w raportach ksiąg VAT zakupu i sprzedaży:

- **PurchaseItemTypeLookup** > Kolumna O: typ pozycji
- **VATRateTypeLookup** > Kolumna B: Typ podatku
- **VATRateTypeLookup** > Kolumna C: Typ pozycji w tabeli
- **PurchaseOperationTypeLookup** > Kolumna A: typ dokumentu
- **CustomerTypeLookup** > kolumna A: typ dokumentu
- **SalesOperationTypeLookup** > Kolumna N: typ operacji
- **SalesItemTypeLookup** > Kolumna O: typ pozycji

Wykonaj następujące kroki, aby skonfigurować różne wyszukiwania używane do generowania deklaracji VAT i powiązanych raportów księgowych. 

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz **Konfiguracje** > **Konfiguracja**, aby skonfigurować reguły identyfikujące transakcję podatkową w powiązanym polu formularza zwrotu podatku VAT.
2. Wybierz bieżącą wersję, a na skróconej karcie **Wyszukiwania** wybierz nazwę wyszukiwania. Na przykład **SalesItemTypeLookup**. To wyszukiwania identyfikują listę klasyfikacji w księdze VAT wymaganych przez urząd skarbowy.
3. Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**, a w nowym wierszu w kolumnie **Wynik wyszukiwania** zaznacz powiązany wiersz reprezentujący klasyfikację w **Kolumnie O**.
4. W kolumnie **Grupa podatków** wybierz grupę podatków używaną do identyfikacji klasyfikacji. Na przykład **Krajowa faktura sprzedaży**. Możesz również użyć grupy podatków dla towaru, kodu podatku lub kombinacji atrybutów drzewa, jeśli konfiguracja jest zdefiniowana w inny sposób. 
5. W kolumnie **Nazwa** wybierz klasyfikację transakcji podatkowych.
6. Powtórz kroki 3–5 dla wszystkich dostępnych wyszukiwania.
7. Wybierz opcję **Dodaj**, aby uwzględnić ostateczny wiersz rekordu, a następnie w kolumnie **Wynik wyszukiwania** wybierz opcję **Nie dotyczy**. 
8. W kolumnach pozostałych wybierz opcję **Niepuste**. 
9. W polu **Stan** wybierz opcję **ukończone**.
10. Wybierz **Zapisz**, a następnie zamknij stronę **Parametry specyficzne dla aplikacji**.

> [!NOTE]
> Podczas dodawania ostatniego rekordu, **Nie dotyczy**, należy zdefiniować następującą regułę: Gdy grupa podatków, grupa podatków towaru, kod podatku i nazwa przekazana jako argument nie spełniają żadnej z poprzednich reguł, transakcje nie są uwzględnione w księdze VAT sprzedaży. Ta reguła nie jest używana podczas generowania raportu, ale pomaga uniknąć błędów w generowaniu raportu w przypadku brakujących konfiguracji reguł.

Poniższe tabele stanowią przykład sugerowanej konfiguracji w opisanych konfiguracjach wyszukiwania. 

**SalesItemTypeLookup**

| Wynik wyszukiwania         | Wiersz | Grupa podatków    | Grupa podatków dla pozycji    | Kod podatku (kod) | Imię i nazwisko                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Krajowe              | 1    | VAT_LOCAL          | *Niepuste*             | *Niepuste*     | Sprzedaż                 |
| Krajowe              | 2    | VAT_LOCAL          | *Niepuste*             | *Niepuste*     | SalesCreditNote       |
| Krajowe              | 3    | VAT_FINALC         | *Niepuste*             | *Niepuste*     | Sprzedaż                 |
| Krajowe              | 4    | VAT_FINALC         | *Niepuste*             | *Niepuste*     | SalesCreditNote       |
| Krajowe              | 5    | VAT_PUBLIO         | *Niepuste*             | *Niepuste*     | Sprzedaż                 |
| Krajowe              | 6    | VAT_PUBLIO         | *Niepuste*             | *Niepuste*     | SalesCreditNote       |
| Eksportowanie                | 7    | VAT_EXPORT         | *Niepuste*             | *Niepuste*     | Sprzedaż                 |
| Eksportowanie                | 8    | VAT_EXPORT         | *Niepuste*             | *Niepuste*     | SalesCreditNote       |
| Maszyny i sprzęt | 9    | *Niepuste*        | VAT_M&E                 | *Niepuste*     | Sprzedaż                 |
| Maszyny i sprzęt | 10   | *Niepuste*        | VAT_M&E                 | *Niepuste*     | SalesCreditNote       |
| Części do maszyn        | 11   | *Niepuste*        | VAT_PARTS               | *Niepuste*     | Sprzedaż                 |
| Części do maszyn        | 12   | *Niepuste*        | VAT_PARTS               | *Niepuste*     | SalesCreditNote       |
| Wyjątki            | 13   | VAT_EXE            | *Nie   puste*           | *Niepuste*     | SaleExempt            |
| Wyjątki            | 14   | VAT_EXE            | *Nie   puste*           | *Niepuste*     | SalesExemptCreditNote |
| Nie dotyczy        | 15   | *Pusty*            | *Pusty*                 | VAT_ADJ         | *Niepuste*           |
| Nie dotyczy        | 16   | *Niepuste*        | *Niepuste*             | *Niepuste*     | *Niepuste*           |

 **SalesOperationTypeLookup**

| Wynik wyszukiwania  | Wiersz | Grupa podatków dla pozycji    | Kod podatku    | Imię i nazwisko                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Towary          | 1    | VAT_GOODS               | *Niepuste* | Sprzedaż                 |
| Towary          | 2    | VAT_GOODS               | *Niepuste* | SalesCreditNote       |
| Towary          | 3    | VAT_GOODS               | *Niepuste* | SaleExempt            |
| Towary          | 4    | VAT_GOODS               | *Niepuste* | SalesExemptCreditNote |
| Usługi       | 5    | VAT_SERV                | *Niepuste* | Sprzedaż                 |
| Usługi       | 6    | VAT_SERV                | *Niepuste* | SalesCreditNote       |
| Usługi       | 7    | VAT_SERV                | *Niepuste* | SaleExempt            |
| Usługi       | 8    | VAT_SERV                | *Niepuste* | SalesExemptCreditNote |
| Korekty    | 9    | *Pusty*                 | VAT_ADJ     | Sprzedaż                 |
| Korekty    | 10   | *Pusty*                 | VAT_ADJ     | SalesCreditNote       |
| Nie dotyczy | 11   | *Niepuste*             | *Niepuste* | *Niepuste*           |

**PurchaseItemTypeLookup**

| Wynik wyszukiwania          | Wiersz | Grupa podatków dla pozycji    | Kod podatku    | Imię i nazwisko                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Towary                  | 1    | VAT_GOODS               | *Niepuste* | Zakup                 |
| Towary                  | 2    | VAT_GOODS               | *Niepuste* | PurchaseCreditNote       |
| Usługi               | 3    | VAT_SERV                | *Niepuste* | Zakup                 |
| Usługi               | 4    | VAT_SERV                | *Niepuste* | PurchaseCreditNote       |
| Maszyny i sprzęt  | 5    | VAT_M&E                 | *Niepuste* | Zakup                 |
| Maszyny i sprzęt  | 6    | VAT_M&E                 | *Niepuste* | PurchaseCreditNote       |
| Części do maszyn         | 7    | VAT_PARTS               | *Niepuste* | Zakup                 |
| Części do maszyn         | 8    | VAT_PARTS               | *Niepuste* | PurchaseCreditNote       |
| Wyjątki             | 9    | VAT_EXE                 | *Nie puste*  | PurchaseExempt           |
| Wyjątki             | 10   | VAT_EXE                 | *Niepuste* | PurchaseExemptCreditNote |
| Nie dotyczy         | 11   | *Niepuste*             | *Niepuste* | *Niepuste*              |

**PurchaseOperationTypeLookup**

| Wynik wyszukiwania  | Wiersz | Grupa podatków  | Kod podatku    | Imię i nazwisko                     |
|----------------|------|------------------|-------------|--------------------------|
| Krajowe       | 1    | VAT_LOCAL        | *Niepuste* | Zakup                 |
| Krajowe       | 2    | VAT_LOCAL        | *Niepuste* | PurchaseCreditNote       |
| Krajowe       | 3    | VAT_LOCAL        | *Niepuste* | PurchaseExempt           |
| Krajowe       | 4    | VAT_LOCAL        | *Niepuste* | PurchaseExemptCreditNote |
| Zaimportowane       | 5    | VAT_IMPORT       | *Niepuste* | Zakup                 |
| Zaimportowane       | 6    | VAT_IMPORT       | *Niepuste* | PurchaseCreditNote       |
| Zaimportowane       | 7    | VAT_IMPORT       | *Niepuste* | PurchaseExempt           |
| Zaimportowane       | 8    | VAT_IMPORT       | *Niepuste* | PurchaseExemptCreditNote |
| Korekty    | 9    | *Pusty*          | VAT_ADJ     | PurchaseCreditNote       |
| Korekty    | 10   | *Pusty*          | VAT_ADJ     | Zakup                 |
| Nie dotyczy | 11   | *Niepuste*      | *Niepuste* | *Niepuste*              |

**CustomerTypeLookup**

|    Wynik wyszukiwania    | Wiersz | Grupa podatków |
|---------------------|------|-----------------|
| Organizacja        |  1   | VAT_LOCAL       |
| Organizacja        |  2   | VAT_EXPORT      |
| Organizacja        |  3   | VAT_EXE         |
| Ostateczny konsument      |  4   | VAT_FINALC      |
| Organizacja publiczna |  5   | VAT_PUBLIO      |
| Nie dotyczy      |  6   | *Niepuste*     |

**VATRateTypeLookup**

| Wynik wyszukiwania  | Wiersz | Kod podatku (kod) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Niepuste*     |
| SecondTable    | 4    | *Niepuste*     |
| Nie dotyczy | 5    | *Niepuste*     |


## <a name="set-up-general-ledger-parameters"></a>Konfigurowanie parametrów księgi głównej

Aby wygenerować raport formularza zwrotu podatku VAT w formacie Microsoft Excel, zdefiniuj format raportu elektronicznego na stronie **Parametry księgi głównej**.

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry księgi głównej**.
2. Na karcie **Podatek**, w sekcji **Opcje podatku**, w polu **Mapowanie formatu deklaracji VAT** wybierz opcję **Deklaracja VAT Excel (EG)**. Jeśli pole to jest puste, standardowy raport podatku zostanie wygenerowany w formacie SSRS.
3. Wybierz **Hierarchię kategorii**. Ta kategoria umożliwia kod towaru w transakcjach na karcie Handel zagraniczny, aby umożliwić użytkownikom wybieranie i klasyfikowanie towarów i usług. Opis tej klasyfikacji jest szczegółowy w raportach transakcji sprzedaży i zakupu. Ta konfiguracja jest opcjonalna.

![Formularz deklaracji.](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Wygeneruj raport zwrotu VAT
Proces przygotowania i przesłania raportu deklaracji VAT za dany okres jest oparty na transakcjach płatności podatku, które zostały zaksięgowane podczas zadania Rozlicz i zaksięguj podatek. Aby uzyskać więcej informacji na temat rozliczania i raportowania podatku od sprzedaży, zobacz [Omówienie podatku](../general-ledger/indirect-taxes-overview.md).

Aby wygenerować raport deklaracji podatkowej, należy wykonać następujące kroki.

1. Przejdź do **Podatek** > **Deklaracje** > **Podatek** > **Raportuj podatek dla okresu rozliczeniowego** lub **Rozlicz i zaksięguj podatek**.
2. Wybierz **Okres rozliczeniowy**.
3. Wybierz datę rozpoczęcia, a następnie wersję płatności podatku.
5. Kliknij przycisk **OK**. 
6. Wprowadź kwotę kredytu z poprzedniego okresu, jeśli ma zastosowanie, lub pozostaw kwotę jako zerową.
7. W polu **Szczegóły raportów** wybierz jedną z dostępnych opcji 
   - **Księga VAT zakupów**: generowanie raportu szczegółów transakcji podatkowych zakupu.
   - **Księga VAT sprzedaży**: generowanie raportu szczegółów transakcji podatkowych sprzedaży.
   - **Deklaracja VAT**: Generuj tylko formularz deklaracji zwrotu VAT.
8. Umożliwia wprowadzenie nazwiska zarejestrowanej osoby, która ma przypisać formularz.
9. Wybierz język. Wszystkie raporty są tłumaczone w języku **en-us** i **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]



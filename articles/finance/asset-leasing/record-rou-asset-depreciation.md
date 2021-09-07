---
title: Rejestrowanie amortyzacji składnika majątku z prawem do użytkowania (wersja zapoznawcza)
description: W tym temacie opisano sposób tworzenia wpisu w arkuszu dla amortyzacji wymaganej dla wynajmów, które są ujmowane w bilansie organizacji.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseAssetSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 02364a0871e9a54f52c7c526cd1897165d52ec68
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345377"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Rejestrowanie amortyzacji składnika majątku z prawem do użytkowania (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


W przypadku wynajmów, które są ujmowane w bilansie organizacji, składnik majątku z prawem do użytkowania (PDU) jest amortyzowany miesięcznie. W tym temacie opisano sposób tworzenia wpisu w arkuszu dla tej amortyzacji. Amortyzacja powoduje obciążenie konta księgowego wydatków i uznanie konta księgowego umorzenia zgodnie z konfiguracją profilu księgowania oraz typem wynajmu. Te wpisy można tworzyć dla każdej umowy wynajmu albo zbiorczo dla wielu umów wynajmu, używając funkcji arkusza przetwarzania wsadowego.

## <a name="asset-depreciation-schedule"></a>Harmonogram amortyzacji składnika majątku

1. Na stronie **Podsumowanie wynajmu** wybierz umowę wynajmu. Następnie wybierz kolejno opcje **Księgi \> Harmonogram amortyzacji składników majątku**, aby otworzyć stronę **Harmonogram amortyzacji składników majątku**.

    Wpis w arkuszu dotyczący wydatku amortyzacji składnika majątku z PDU jest oparty na kwocie z kolumny **Wydatek amortyzacji**. Aby zapoznać się z przykładem wytycznych dotyczących przestrzegania standardów rachunkowości, zajrzyj do sekcji [Obliczanie wydatku z tytułu amortyzacji składnika majątku z PDU w umowach leasingu finansowego](#calculation-of-rou-asset-amortization-expense-for-finance-leases) w dalszej części tego tematu.

2. Wybierz okres amortyzacji, a następnie wybierz opcję **Utwórz arkusz**. Zostanie wyświetlony komunikat informujący o utworzeniu arkusza, który będzie używany do rejestrowania amortyzacji.
3. Wybierz kolejno opcje **Arkusze \> Arkusze wynajmu składnika majątku**, aby otworzyć stronę **Arkusz wynajmu składnika majątku**, na której można przejrzeć utworzony wpis w arkuszu dotyczący wydatku amortyzacji.

   System blokuje możliwość edytowania niektórych pól finansowych, aby zapobiec ewentualnym rozbieżnościom między transakcjami a harmonogramami. Do blokowanych pól należą m.in. następujące: **Konto**, **Kwoty**, **Wymiary finansowe**, **Waluta** i **Typ transakcji**. Ponadto nie można dodawać ani usuwać wierszy wpisów w arkuszu w żadnych wpisach arkusza wynajmu składnika majątku, ponieważ mogłoby to spowodować rozbieżności między harmonogramami a transakcjami.

4. Wybierz wpis w arkuszu, a następnie wybierz opcję **Księguj**, aby zarejestrować wpis amortyzacji w księdze głównej.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Obliczanie wydatku z tytułu amortyzacji składnika majątku z PDU w umowach leasingu finansowego

Wydatek amortyzacji w leasingu operacyjnym jest obliczany jako różnica między liniowym miesięcznym wydatkiem na wynajem a miesięcznym kosztem odsetek w zobowiązaniu z tytułu wynajmu zgodnie z zasadami Accounting Standards Codification Topic 842 (ASC 842), które są standardem przyjętym w ogólnie przyjętych zasadach rachunkowości w Stanach Zjednoczonych (US GAAP). Liniowy wydatek na wynajem jest obliczany poprzez zsumowanie wszystkich opłat z tytułu wynajmu, a następnie ich podzielenie przez okres wynajmu w miesiącach. (Suma opłat z tytułu wynajmu obejmuje wszelkie przedpłaty, początkowe koszty bezpośrednie, koszty demontażu i prowizje stymulujące wynajem). W poniższej tabeli przedstawiono przykład wydatku z tytułu amortyzacji w leasingu operacyjnym.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Przykład wydatku z tytułu amortyzacji składnika majątku z PDU w umowach leasingu operacyjnego

| Pole                                          | Wartość       |
|------------------------------------------------|-------------|
| Kwota płatności                                 | 1 000       |
| Częstość płatności                              | Miesięczne     |
| Okres wynajmu (w miesiącach)                            | 24          |
| Łączne opłaty z tytułu wynajmu                           | 24,000      |
| Krańcowa stopa procentowa                     | 5%          |
| Typ annuity                                   | Należna annuita |
| Interwał łączenia                           | Miesięczne     |
| Wartość bieżąca przyszłych opłat z tytułu wynajmu | 22,888.87   |

Jak już wcześniej wspomniano, liniowy wydatek na wynajem jest obliczany poprzez zsumowanie wszystkich opłat, a następnie ich podzielenie przez okres wynajmu. System automatycznie obliczy miesięczny koszt odsetek dla harmonogramu amortyzacji zobowiązań. Koszt odsetek jest obliczany przy użyciu metody efektywnej stopy procentowej. System zastosuje liniowy koszt wynajmu do odjęcia kosztu odsetek za każdy miesiąc. Ta wartość zostanie użyta do zmniejszania wartości składnika majątku z PDU.

| Miesiąc | Liniowy koszt wynajmu | Odsetki                        | Obliczanie wydatku z tytułu amortyzacji składnika majątku z PDU |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24 000 ÷ 24) = 1000,00 | (22 888,87 – 1000) × (5% ÷ 12) = 91,20 | 1000 – 91,20 = 908,80                        |
| 2     | (24 000 ÷ 24) = 1000,00 | (21 980,08 – 1000) × (5% ÷ 12) = 87,42 | 1000 – 87,42 = 912,58                        |
| 3     | (24 000 ÷ 24) = 1000,00 | (21 067,49 – 1000) × (5% ÷ 12) = 83,62 | 1000 – 83,62 = 916,39                        |

> [!NOTE]
> Zgodnie ze standardem ASC 842 amortyzacja składnika majątku z PDU dla leasingu operacyjnego jest klasyfikowana jako wydatek z tytułu wynajmu w rachunku zysków i strat. Dla lepszej przejrzystości moduł Wynajem składnika majątku opisuje wpis jako amortyzację składnika majątku z PDU. Jednak zapis debetowy powinien być przypisany do konta wydatków leasingu operacyjnego, a zapis kredytowy powinien być przypisany bezpośrednio do składnika majątku z PDU w leasingu operacyjnym. Niemniej jednak w parametrach wynajmu można określić, że dla składników majątku z PDU w umowach leasingu operacyjnego należy dokonać zapisów kredytowych na koncie umorzenia.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Obliczanie wydatku z tytułu amortyzacji składnika majątku z PDU w umowach leasingu operacyjnego

W umowach wynajmu zaklasyfikowanych jako leasing finansowy system oblicza amortyzację składnika majątku z PDU metodą liniową. Z tego powodu wydatek amortyzacji będzie taki same w każdym miesiącu.

Zgodnie z Międzynarodowym Standardem Sprawozdawczości Finansowej nr 16 (MSSF 16) i standardem ASC 842 składnik majątku będzie amortyzowany przez okres wynajmu lub okres użyteczności składnika, w zależności od tego, który z nich jest krótszy. Ponadto jeśli dla wynajmu jest włączony parametr **Przeniesienie własności**, przedmiot wynajmu będzie automatycznie amortyzowany przez okres użyteczności składnika majątku.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Przykład wydatku z tytułu amortyzacji składnika majątku z PDU w umowach leasingu finansowego

| Pole                                | Wartość                                   |
|--------------------------------------|-----------------------------------------|
| Początkowe saldo wartości składnika majątku z prawem do użytkowania | 22,889.87                               |
| Okres wynajmu (w miesiącach)                  | 24                                      |
| Okres użyteczności składnika majątku (w miesiącach)           | 36                                      |
| Miesiąc                                | Wydatek z tytułu amortyzacji składnika majątku z prawem do użytkowania |
| 1                                    | 22 889,87 ÷ 24 = 953,74                 |
| 2                                    | 22 889,87 ÷ 24 = 953,74                 |
| 3                                    | 22 889,87 ÷ 24 = 953,74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

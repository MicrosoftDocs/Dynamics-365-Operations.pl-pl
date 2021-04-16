---
title: Termin wystawienia faktury
description: W tym artykule omówiono konfigurowanie parametrów obliczania terminów wystawiania faktur dla odbiorcy i faktur od dostawcy w Unii Europejskiej (UE).
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.reviewer: kfend
ms.custom: 10923
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95505808bd7df29de97ff204a95fe294f293bb0c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814984"
---
# <a name="invoice-issue-deadline"></a>Termin wystawienia faktury

[!include [banner](../includes/banner.md)]

W tym artykule omówiono konfigurowanie parametrów obliczania terminów wystawiania faktur dla odbiorcy i faktur od dostawcy w Unii Europejskiej (UE).

Dyrektywa Unii Europejskiej (UE) 45/2010 i inne dyrektywy wymagają, aby wysyłki w obrębie UE (wysyłki wewnątrzunijne) były fakturowane do piętnastego dnia miesiąca włącznie od daty zrealizowania dostawy. Jednocześnie w poszczególnych państwach członkowskich UE mogą obowiązywać różne terminy fakturowania dla dostaw krajowych. Funkcja terminu wystawienia faktury pozwala przypisać zakres dat do typu kraju/regionu. Następnie, dla wszystkich wysyłek do i z kraju/regionu określonego typu termin wystawienia faktury jest obliczany za pomocą reguł ustawionych w określonym zakresie dat. Ponadto można uzyskać wszystkie dokumenty dostawy z określonym terminem wystawienia faktury, filtrować termin wystawienia faktury podczas okresowego fakturowania sprzedaży i kontrolować datę wystawienia faktury sprzedaży podczas księgowania faktury. Możesz ustawić kod zakresu dat, a następnie skonfigurować regułę obliczania terminu wystawienia faktury poprzez przypisanie kodu zakresu dat do typu kraju/regionu. Reguła obliczania jest używana do obliczania terminu wystawiania faktur w przypadku następujących transakcji:

-   Wysyłki wewnątrzunijne
-   Krajowe wysyłki w ramach Unii Europejskiej

Można także skonfigurować kontrolę daty, aby zapewnić, że faktury dla odbiorców i faktury korygujące za transakcje klientów są generowane w ciągu określonego okresu po dokonaniu dostawy.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą zostać spełnione, aby używać funkcji terminu wystawienia faktury.

| Kategoria            | Wymaganie wstępne                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kraj/region      | Podstawowy adres firmy musi być w Unii Europejskiej.                                                                                                                                                                                                                                                                                                                    |
| Pokrewne zadania konfiguracji | Na stronie **Zakresy dat** ustaw zakres dat, który jest używany do obliczania terminu wystawienia faktury. (Kliknij kolejno opcje **Księga główna** &gt; **Ustawienia księgi** &gt; **Zakresy dat**). Na stronie **Parametry handlu zagranicznego** ustaw właściwości handlu zagranicznego dla różnych krajów/regionów. (Kliknij kolejno opcje **Podatek** &gt; **Ustawienia** &gt; **Handel zagraniczny** &gt; **Parametry handlu zagranicznego**). |

## <a name="invoice-issue-due-date-calculation-rule"></a>Reguła obliczania terminów wystawiania faktur
Za pomocą strony **Ustaw obliczanie dla terminu wystawienia faktury** ustaw regułę obliczania terminu wystawienia faktury poprzez przypisanie kodu zakresu dat do typu kraju/regionu.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Parametry kontroli daty dla faktur dla odbiorców i faktur korygujących
Można także skonfigurować parametry kontroli daty, aby zapewnić, że faktury dla odbiorców i faktury korygujące za transakcje klientów są generowane w ciągu określonego okresu po dokonaniu dostawy. Można znaleźć te parametry w obszarze **Kontrola daty faktury** na stronie **Parametry rozrachunków z odbiorcami**.

## <a name="example"></a>Przykład
Aby obliczyć terminy wystawiania faktur do wysyłki wewnątrz UE na 15. dzień miesiąca po miesiącu, w którym dostawa została zrealizowana, utwórz kod interwału daty i regułę obliczania za pomocą następujących ustawień.

### <a name="date-interval-code"></a>Kod zakresu dat

| Pole                                                           | Wartość                           |
|-----------------------------------------------------------------|---------------------------------|
| Kod zakresu dat                                              | 15-NM                           |
| Opis                                                     | 15. dzień kolejnego miesiąca |
| Przed (w grupie pól **Do dnia**)                         | Miesiąc                           |
| Początek/koniec (w grupie pól **Do dnia**)                      | Zamknij                             |
| +/- (w grupie pól **Do dnia**)                            | 15                              |
| Dni, miesiące, lata lub okresy (w grupie pól **Do dnia**) | Dni                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Reguła obliczania terminów wystawiania faktur

| Pole               | Wartość                                                     |
|---------------------|-----------------------------------------------------------|
| Typ kraju/regionu | **UE**                                                    |
| Data początkowa          | Służy do wprowadzania daty, kiedy zaczyna obowiązywać ustawienie bieżącego wiersza. |
| Kod zakresu dat  | **15-NM**                                                 |

## <a name="next-steps"></a>Następne kroki
Po zakończeniu konfigurowania parametrów obliczania terminu wystawienia faktury można tworzyć i księgować transakcje wymienione poniżej w celu automatycznego obliczania i aktualizowania terminów wystawiania faktur:

-   **Zamówienia sprzedaży** — podczas tworzenia zamówienia sprzedaży i księgowania dokumentu dostawy termin wystawienia faktury jest obliczany i aktualizowany na dokumencie dostawy. Termin jest obliczany na podstawie zakresu dat przypisanego do kraju/regionu określonego w adresie dostawy zamówienia sprzedaży. Po zaksięgowaniu dokumentu dostawy można sprawdzić termin wystawienia faktury w polu **Termin wystawienia faktury** na stronie **Arkusz dokumentu dostawy**. (Kliknij kolejno opcje **Sprzedaż i marketing** &gt; **Zamówienie sprzedaży** &gt; **Wysyłka zamówienia** &gt; **Dokument dostawy**). Na stronie **Niezafakturowane dokumenty dostawy** możesz wyświetlić wszystkie niezafakturowane dokumenty dostawy oraz ich terminy wystawienia faktury. (Kliknij kolejno opcje **Sprzedaż i marketing** &gt; **Zamówienie sprzedaży** &gt; **Wysyłka zamówienia** &gt; **Niezafakturowane dokumenty dostawy**.)
-   **Zamówienia zakupu** — podczas tworzenia zamówienia zakupu i księgowania dokumentu przyjęcia produktów termin wystawienia faktury jest obliczany i aktualizowany na dokumencie przyjęcia produktów. Termin jest obliczany na podstawie interwału dat przypisanego do kraju/regionu określonego w podstawowym adresie dostawcy. Po zaksięgowaniu dokumentu przyjęcia produktów, można sprawdzić datę wystawienia faktury w polu **Data wystawienia faktury** na stronie **Arkusz dokumentu przyjęcia produktów**. (Kliknij kolejno opcje **Zaopatrzenie i sourcing** &gt; **Zamówienia zakupu** &gt; **Przyjęcia produktów** &gt; **Dokument przyjęcia produktów**). Na stronie **Niezafakturowane dokumenty przyjęcia produktów** możesz wyświetlić wszystkie niezafakturowane dokumenty przyjęcia produktów oraz ich terminy wystawienia faktury. (Kliknij kolejno opcje **Zaopatrzenie i sourcing** &gt; **Zamówienia zakupu** &gt; **Przyjęcia produktów** &gt; **Niezafakturowane dokumenty przyjęcia produktów**).

## <a name="technical-information-for-system-administrators"></a>Informacje techniczne dla administratorów systemu
Jeśli nie masz dostępu do stron, które są używane do ukończenia zadań opisanych w tym artykule, skontaktuj się z administratorem systemu i podaj informacje, które przedstawiono w poniższej tabeli.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategoria</th>
<th>Wymaganie wstępne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Keys</td>
<td>Kliknij kolejno opcje <strong>Administrowanie systemem</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Licencjonowanie</strong> &gt; <strong>Konfiguracja licencji</strong>. Kliknij klucz konfiguracji <strong>Księga główna</strong>.</td>
</tr>
<tr class="even">
<td>Role zabezpieczeń i obowiązki</td>
<td>Aby wykonać to zadanie, musisz być członkiem roli zabezpieczeń uwzględniającej następujące obowiązki:
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (Włączanie procesu faktur i gotówki)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (Włączanie procesu faktur i płatności)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Role i uprawnienia zabezpieczeń</td>
<td>Aby wykonać to zadanie, musisz być członkiem roli zabezpieczeń uwzględniającej następujące przywileje:
<ul>
<li><strong>CustPackingSlipJournalView</strong> (Wyświetlanie dokumentów dostawy sprzedaży)</li>
<li><strong>VendPackingSlipJournalView</strong> (Przeglądanie arkusza dokumentu przyjęcia produktów z zamówienia zakupu)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (Obliczanie terminów wystawienia faktur)</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
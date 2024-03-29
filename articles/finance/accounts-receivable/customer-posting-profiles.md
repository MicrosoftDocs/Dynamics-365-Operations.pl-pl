---
title: Profile księgowania klientów
description: Ten artykuł opisuje profile księgowania klientów, które kontrolują księgowanie transakcji klientów do księgi głównej.
author: JodiChristiansen
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04cf5b8656bccde974fb1adfdf830080e2f52436
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799580"
---
# <a name="customer-posting-profiles"></a>Profile księgowania klientów

[!include [banner](../includes/banner.md)]

Ten artykuł opisuje profile księgowania klientów, które kontrolują księgowanie transakcji klientów do księgi głównej.

## <a name="customer-posting-profiles"></a>Profile księgowania odbiorców

Profile księgowania odbiorców pozwalają na przypisywanie kont księgi głównej i ustawień dokumentów do wszystkich odbiorców, grupy odbiorców lub jednego odbiorcy. Te ustawienia będą używane podczas tworzenia faktur zleceń sprzedaży, faktur z wolnym tekstem, faktur projektowych, dzienników płatności, listów windykacyjnych i not odsetkowych. 

Domyślny profil księgowania jest zdefiniowany na skróconej karcie **Księga i podatek** na stronie **parametrów rozrachunków z odbiorcami**. Jest on wtedy automatycznie umieszczany w nagłówku nowych dokumentów. Możesz go tam zmienić, jeśli wymagany jest inny profil postu. 

Organizacje, które przyjmują przedpłaty od klientów, często konfigurują drugi profil księgowania dla przedpłat i łączą go w parametrach jako domyślny profil księgowania dla przedpłat. Aby uzyskać więcej informacji, zobacz [Przedpłaty klientów](customer-prepayments.md).

Można także skojarzyć definicje księgowania transakcji z typami księgowania transakcji na stronie **Definicje księgowania transakcji** . Definicje księgowań są używane zamiast profili księgowań do kontrolowania księgowania transakcji klientów w księdze głównej. Aby uzyskać więcej informacji, zobacz [Definicje księgowania](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Tworzenie profilu księgowania
Służy do określania kont księgowych używanych podczas księgowania transakcji z wybranym profilem księgowania. Służy do wybierania kodu konta i, jeżeli jest to możliwe, numeru konta lub grupy dla wybranego profilu księgowania. W procesie księgowania najodpowiedniejszy profil księgowania dla każdej transakcji jest wyszukiwany według najbardziej charakterystycznej kombinacji kodu konta, numeru konta lub numeru grupy z następującym priorytetem:

| Wartość pola Kod konta | Wartość pola Numer konta/grupy                | Priorytet wyszukiwania |
|--------------------------|-------------------------------------------------|-----------------|
| Tabela                    | Określone konto odbiorcy.                       | 1 przypada na wpłatę z zysku na rzecz budżetu państwa               |
| Grupa                    | Grupa odbiorców skojarzona z odbiorcą | 2               |
| Wszystko                      | Puste                                           | 3               |

Jeśli wszystkie transakcje klienta mają mieć ten sam profil księgowania, należy ustawić tylko jeden profil księgowania o wartości **Wszystko** w polu **Kod konta**. Określ następujące wartości do konfigurowania profilu księgowania.

<table>
<thead>
<tr>
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Profil księgowania</strong></td>
<td>Umożliwia wprowadzenie kodu profilu księgowania. Można na przykład utworzyć 2 profile księgowania, aby korzystać z jednego konta dla sald odbiorcy w walucie krajowej, a z drugiego — dla sald odbiorcy w walucie zagranicznej. Jedno konto można nazwać Krajowe, a drugie Zagraniczne.</td>
</tr>
<tr>
<td><strong>Opis</strong></td>
<td>Umożliwia wprowadzenie opisu profilu księgowania. To jest używane jedynie, aby lepiej określić profil księgowania, podczas przeglądania tej strony.</td>
</tr>
<tr>
<td><strong>Kod konta</strong></td>
<td>Umożliwia określenie, czy profil księgowania dotyczy jednego odbiorcy, grupy odbiorców czy wszystkich odbiorców:
<ul>
<li><b>Tabela</b> — profil księgowania dotyczy jednego odbiorcy. Wybierz konto odbiorcy w polu <b>Numer konta/grupy</b>.</li>
<li><b>Grupa</b> — profil księgowania dotyczy grupy odbiorców. Wybierz grupę odbiorców w polu <b>Numer konta/grupy</b>.</li>
<li><b>Wszyscy</b> — profil księgowania dotyczy wszystkich odbiorców. Pole <b>Numer konta/ Numer grupy</b> zostaw niewypełnione.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Numer konta/grupy</strong></td>
<td>W przypadku wybrania opcji <b>Tabela</b> w polu <b>Kod konta</b> należy wybrać numer konta odbiorcy skojarzony z profilem księgowania. W przypadku wybrania opcji <b>Grupa</b> zaznacz grupę odbiorców. W przypadku wybrania opcji <b>Wszystko</b> należy pozostawić to pole puste.</td>
</tr>
<tr>
<td><strong>Konto rozrachunkowe</strong></td>
<td>Wybierz konto główne, które będzie używane jako konto handlowe dla klientów, którzy są powiązani z profilem księgowania. To konto jest kontem typu księgowania <b>salda klienta</b>.</td>
</tr>
<tr>
<td><strong>Konto płynności dla płatności</strong></td>
<td>Umożliwia wybranie <strong>Konta płynności księgi głównej</strong> używanego przy prognozowaniu przepływów pieniężnych. To pole będzie dostępne tylko wtedy, gdy prognozy przepływów gotówkowych są dozwolone.</td>
</tr>
<tr>
<td><strong>Przedpłaty podatku</strong></td>
<td><p>Wybierz konto dla płatności podatków z góry.</p>
<p><strong>Uwaga:</strong> Aby określić profil księgowania używany, gdy płatność jest oznaczona jako przedpłata, należy użyć strony <b>parametrów rozrachunków z odbiorcami</b>.</p>
</td>
</tr>
<tr>
<td><strong>Konto zobowiązań związanych z rabatami</strong></td>
<td>Umożliwia wybranie konta księgowego dla księgowania rabatu.</td>
</tr>
<tr>
<td><strong>Kolejność ponagleń</strong></td>
<td>Umożliwia wybranie identyfikatora kolejności ponagleń dla odbiorców, do których jest przypisany profil księgowania.</td>
</tr>
<tr>
<td><strong>Kod odsetek</strong></td>
<td>Umożliwia wstawienie kodu używanego do obliczeń odsetek dla odbiorców, do których jest przypisany profil księgowania.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Przykłady księgowania

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami. Kolumna **Debet/Kredyt** wskazuje, czy transakcja zazwyczaj ma być księgowana po stronie debetowej lub kredytowej, czy w niektórych przypadkach po stronie obydwu. Kolumna **Konto rozliczeniowe** wskazuje typ księgowania jako konto rozliczeniowe. Oznacza to, że kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji. 

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Saldo odbiorcy | 130100 | Należności handlowe | Element zawartości | Obie | Nie | Określ konto w polu **Konto podsumowujące**.|
| Brak | 110110 | Konto bankowe | Element zawartości | Obie | Nie | W polu **Konto płynnościowe dla płatności** podaj rachunek główny. To konto nie jest używane do księgowania. Służy tylko do prognozowania przepływów pieniężnych. |
| Przedpłaty podatku | 202900 | Rozliczanie podatku od sprzedaży | Pasywa | Obie | Tak | Wybierz konto dla płatności podatków z góry. |
| Konto zobowiązań związanych z rabatami | 250600 | Przychody przyszłych okresów i rabaty | Pasywa | Obie | Tak | Umożliwia wybranie konta księgowego dla księgowania rabatu.|     

### <a name="table-restrictions"></a>Restrykcje tabeli

Dla transakcji z tym profilem księgowania określ, czy transakcje będą rozliczane automatycznie, czy będą obliczane odsetki i czy będą wysyłane ponaglenia. Można również wybrać konto, które będzie używane podczas zamykania transakcji z wybranym profilem księgowania.

Określ następujące wartości do konfigurowania profilu księgowania:

| Pole                 | Opis                                           |
|-----------------------|-------------------------------------------------------|
| Miejscowość        | Wybierz tę opcję, aby włączyć automatyczne rozliczanie transakcji, które mają ten profil księgowania. Jeśli ta opcja jest wyczyszczona, należy ręcznie rozliczyć transakcje na stronie **Rozliczanie otwartych transakcji** lub **Wprowadzanie płatności odbiorcy**. |
| Zainteresowania          | Wybierz tę opcję, jeśli odsetki powinny być obliczane według niezapłaconych sald dla kont odbiorców z tym profilem. Jeśli ta opcja jest wyczyszczona, odsetki dla tych odbiorców nie będą obliczane.                                           |
| Ponaglenie | Wybierz tę opcję, jeśli ponaglenia powinny być generowane dla kont odbiorców z tym profilem. Jeśli ta opcja jest wyczyszczona, ponaglenia dla tych odbiorców nie będą generowane.                                                 |
| Zamknij             | Umożliwia wybranie docelowego profilu księgowania, który ma zostać włączony po zamknięciu transakcji bieżącego profilu księgowania. Transakcja jest traktowana jako zamknięta, jeśli jest w pełni rozliczona.             |



Aby uzyskać więcej informacji, zobacz [Przegląd płatności odbiorców](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

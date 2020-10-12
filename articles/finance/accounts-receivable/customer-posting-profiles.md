---
title: Profile księgowania odbiorców
description: Profile księgowania odbiorców sterują księgowaniem transakcji z odbiorcami w księdze głównej.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff786d6e872e48f9605f9a472b7bffd409c5b3f
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830581"
---
# <a name="customer-posting-profiles"></a>Profile księgowania odbiorców

[!include [banner](../includes/banner.md)]

Profile księgowania odbiorców sterują księgowaniem transakcji z odbiorcami w księdze głównej.

<a name="customer-posting-profiles"></a>Profile księgowania odbiorców
-------------------------

Profile księgowania odbiorców pozwalają na przypisywanie kont księgi głównej i ustawień dokumentów do wszystkich odbiorców, grupy odbiorców lub jednego odbiorcy. Te ustawienia będą obowiązywać podczas tworzenia zamówień sprzedaży, faktur niezależnych, płatności gotówką, ponagleń i not odsetkowych. W przypadku niektórych transakcji można wybrać profil księgowania, który różni się od profilów księgowania ustawionych dla transakcji na tej stronie i ma względem nich pierwszeństwo. 

Domyślny profil księgowania jest zdefiniowany na skróconej karcie Księga i podatek na stronie parametrów rozrachunków z odbiorcami. Domyślny profil księgowania jest następnie automatycznie uwzględniany w nagłówku nowych dokumentów, gdzie można go zmienić na inny profil księgowania w razie potrzeby.

Można także skojarzyć definicje księgowania transakcji z typami księgowania transakcji na stronie Definicje księgowania transakcji. Definicja księgowania umożliwia kontrolowanie księgowania transakcji odbiorcy w księdze głównej zamiast przez profile księgowania.

## <a name="creating-a-posting-profile"></a>Tworzenie profilu księgowania
Służy do określania kont księgowych używanych podczas księgowania transakcji z wybranym profilem księgowania. Służy do wybierania kodu konta i, jeżeli jest to możliwe, numeru konta lub grupy dla wybranego profilu księgowania. W procesie księgowania najodpowiedniejszy profil księgowania dla każdej transakcji jest wyszukiwany według najbardziej charakterystycznej kombinacji kodu konta, numeru konta lub numeru grupy z następującym priorytetem:

| Wartość pola **Kod konta** | Wartość pola **Numer konta/grupy**            | Priorytet wyszukiwania |
|------------------------------|-------------------------------------------------|-----------------|
| **Tabela**                    | Określone konto odbiorcy.                       | 1 przypada na wpłatę z zysku na rzecz budżetu państwa               |
| **Grupa**                    | Grupa odbiorców skojarzona z odbiorcą | 2               |
| **Wszystkie**                      | Puste                                           | 3               |

Jeśli wszystkie transakcje odbiorcy mają mieć ten sam profil księgowania, należy ustawić tylko jeden profil księgowania o wartości Wszystko polu Kod konta. Określ następujące wartości do konfigurowania profilu księgowania:

<table>
<thead>
<tr class="header">
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Profil księgowania</strong></td>
<td>Umożliwia wprowadzenie kodu profilu księgowania. Można na przykład utworzyć 2 profile księgowania, aby korzystać z jednego konta dla sald odbiorcy w walucie krajowej, a z drugiego — dla sald odbiorcy w walucie zagranicznej. Jedno konto można nazwać Krajowe, a drugie Zagraniczne.</td>
</tr>
<tr class="even">
<td><strong>Opis</strong></td>
<td>Umożliwia wprowadzenie opisu profilu księgowania. To jest używane jedynie, aby lepiej określić profil księgowania, podczas przeglądania tej strony.</td>
</tr>
<tr class="odd">
<td><strong>Kod konta</strong></td>
<td>Umożliwia określenie, czy profil księgowania dotyczy jednego odbiorcy, grupy odbiorców czy wszystkich odbiorców:
<ul>
<li><strong>Tabela</strong> — profil księgowania dotyczy jednego odbiorcy. Wybierz konto odbiorcy w polu Numer konta/grupy.</li>
<li><strong>Grupa</strong> — profil księgowania dotyczy grupy odbiorców. Wybierz grupę odbiorców w polu Numer konta/grupy.</li>
<li><strong>Wszyscy</strong> — profil księgowania dotyczy wszystkich odbiorców. Pole Numer konta/grupy zostaw niewypełnione</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numer konta/grupy</strong></td>
<td>W przypadku wybrania opcji Tabela w polu Kod konta należy wybrać numer konta odbiorcy skojarzony z profilem księgowania. W przypadku wybrania opcji Grupa zaznacz grupę odbiorców. W przypadku wybrania opcji Wszystko należy pozostawić to pole puste.</td>
</tr>
<tr class="odd">
<td><strong>Konto rozrachunkowe</strong></td>
<td>Umożliwia wybranie konta księgowego, które będzie używane jako konto rozrachunkowe odbiorcy dla odbiorców skojarzony z tym profilem księgowania.</td>
</tr>
<tr class="even">
<td><strong>Konto rozliczeniowe</strong></td>
<td>Umożliwia wybranie konta płynności używanego przy prognozowaniu przepływów pieniężnych. To pole będzie dostępne tylko wtedy, gdy prognozy przepływów gotówkowych są dozwolone.</td>
</tr>
<tr class="odd">
<td><strong>Przedpłaty podatku</strong></td>
<td>Wybierz konto dla płatności podatków z góry.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Uwaga" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Uwaga</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aby określić profil księgowania używany, gdy płatność jest oznaczona jako przedpłata, należy użyć strony parametrów rozrachunków z odbiorcami.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Konto zobowiązań związanych z rabatami</strong></td>
<td>Umożliwia wybranie konta księgowego dla księgowania rabatu.</td>
</tr>
<tr class="odd">
<td><strong>Kolejność ponagleń</strong></td>
<td>Umożliwia wybranie identyfikatora kolejności ponagleń dla odbiorców, do których jest przypisany profil księgowania.</td>
</tr>
<tr class="even">
<td><strong>Kod odsetek</strong></td>
<td>Umożliwia wstawienie kodu używanego do obliczeń odsetek dla odbiorców, do których jest przypisany profil księgowania.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Restrykcje tabeli**

Dla transakcji z tym profilem księgowania określ, czy transakcje będą rozliczane automatycznie, czy będą obliczane odsetki i czy będą wysyłane ponaglenia. Można również wybrać konto, które będzie używane podczas zamykania transakcji z wybranym profilem księgowania.

Określ następujące wartości do konfigurowania profilu księgowania:

| Pole                 | Opis                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Rozliczenie**        | Wybierz tę opcję, aby włączyć automatyczne rozliczanie transakcji, które mają ten profil księgowania. Jeśli ta opcja jest wyczyszczona, należy ręcznie rozliczyć transakcje na stronie Rozliczanie otwartych transakcji lub Wprowadzanie płatności odbiorcy. |
| **Zainteresowania**          | Wybierz tę opcję, jeśli odsetki powinny być obliczane według niezapłaconych sald dla kont odbiorców z tym profilem. Jeśli ta opcja jest wyczyszczona, odsetki dla tych odbiorców nie będą obliczane.                                           |
| **Ponaglenie** | Wybierz tę opcję, jeśli ponaglenia powinny być generowane dla kont odbiorców z tym profilem. Jeśli ta opcja jest wyczyszczona, ponaglenia dla tych odbiorców nie będą generowane.                                                 |
| **Zamknij**             | Umożliwia wybranie docelowego profilu księgowania, który ma zostać włączony po zamknięciu transakcji bieżącego profilu księgowania. Transakcja jest traktowana jako zamknięta, jeśli jest w pełni rozliczona.                                                                           |



Aby uzyskać więcej informacji, zobacz [Przegląd płatności odbiorców](../cash-bank-management/tasks/customer-payment-overview.md).


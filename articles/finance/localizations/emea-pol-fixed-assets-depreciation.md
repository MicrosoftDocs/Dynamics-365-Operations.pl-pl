---
title: Amortyzacja środków trwałych dla Polski
description: Ten artykuł zawiera informacje o amortyzowaniu środków trwałych dla firm w Polsce.
author: AdamTrukawka
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 264274
ms.search.form: AssetBook, AssetDepreciationGroup_W, AssetParameters, AssetPosting
ms.openlocfilehash: 54120f19b9c78e935c4a10d3d2687a43a5ed1a93
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274581"
---
# <a name="fixed-assets-depreciation-for-poland"></a>Amortyzacja środków trwałych dla Polski

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o amortyzowaniu środków trwałych dla firm w Polsce.

Funkcje amortyzacji środków trwałych oparte na wymaganiach prawnych w Polsce obejmują następujące elementy:

-   Metody amortyzacji
-   Poziom procentu amortyzacji
-   Grupy amortyzacji
-   Ta sama data, co jest opcją w propozycji amortyzacji. Powoduje ona wypełnianie pola **Data** we wszystkich wierszach arkusza wartością z pola **Do dnia** zdefiniowanego w propozycji amortyzacji.

## <a name="poland-specific-depreciation-methods"></a>Metody amortyzacji specyficzne dla Polski
Dla firm w Polsce istnieją dodatkowe metody, reguły i ustawienia amortyzacji, które są używane do spełnienia określonych wymogów rachunkowości środków trwałych. Zgodnie z polskimi przepisami amortyzacja jest obliczana przy użyciu rocznej stawki amortyzacji. Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [Amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md). Dla firm w Polsce są dostępne następujące metody amortyzacji:

-   **Degresywna (Polska)** — Ta metoda amortyzacji uwzględnia lokalne specjalne wymogi prawne dotyczące zmiany wartości środków trwałych w trakcie roku obrachunkowego i rozpoznawania części kosztowej. Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zwiększenie
    -   Zmniejszenie
    -   Przeszacowanie
    -   Poprzednia amortyzacja
-   **Liniowa (Polska)** — Amortyzacja jest obliczana dla pierwszego okresu na podstawie liczby dni używania środka trwałego. Na przykład jeśli środek trwały zakupiono 15 stycznia, a okres amortyzacji rozpoczyna się 1 stycznia, amortyzacja jest obliczana dla połowy okresu. Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zwiększenie
    -   Zmniejszenie
    -   Przeszacowanie
-   **Liniowa procentowa (Polska)** — Okres użytkowania jest obliczany przez wprowadzenie wartości procentowej i podzielenie 100% przez wprowadzony procent. Na przykład jeśli wprowadzono 20%, 100% podzielone przez 20% to 5 lat użytkowania. Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zwiększenie
    -   Zmniejszenie
    -   Przeszacowanie

Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [Amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md).

## <a name="depreciation-percent-level-parameter"></a>Parametr Poziom procentu amortyzacji
Metody amortyzacji Degresywna (Polska) i Liniowa procentowa (Polska) używają pola **Poziom procentu amortyzacji** znajdującego się na stronie **Parametry środków trwałych**. To pole pozwala wybrać, czy na potrzeby obliczenia amortyzacji poziom procentu amortyzacji ma być pobierany z metody amortyzacji czy z konkretnego środka trwałego:

-   **Profil (standardowy)** — Wybierz tę opcję, aby używać wartości procentowej z** **profilu amortyzacji.
-   **Księga środków trwałych** — Wybierz tę opcję, aby używać tej samej metody amortyzacji. Amortyzacja będzie obliczana przy użyciu wartości procentowej z księgi środków trwałych.

## <a name="depreciation-groups"></a>Grupy amortyzacji
Firmy w Polsce mogą łączyć środki trwałe z grupami amortyzacji. Grupy amortyzacji są definiowane dla księgi środków trwałych w celu określenia szczegółów środków trwałych, takich jak współczynnik podwyższający, współczynnik alternatywny i limit kosztu. Jeśli grupa amortyzacji jest przypisana do środka trwałego, kontroluje kwotę amortyzacji za pomocą współczynnika podwyższającego, przez który jest mnożona kwota amortyzacji. Na stronie **Grupy amortyzacji** można tworzyć i edytować następujące grupy amortyzacji:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Nazwa pola</strong></td>
<td><strong>Opis</strong></td>
</tr>
<tr class="even">
<td><strong>Data początkowa</strong></td>
<td>Dzień, w którym zostaną użyte wartości współczynnika podwyższającego i limitu kosztu.</td>
</tr>
<tr class="odd">
<td><strong>Współczynnik podwyższający</strong></td>
<td>Wskaźnik, przez który jest mnożona kwota amortyzacji. Współczynnik podwyższający można skonfigurować, gdy jest używany profil amortyzacji alternatywnej (współczynnik alternatywny) lub profil amortyzacji dodatkowej (współczynnik dodatkowy).</td>
</tr>
<tr class="even">
<td><strong>Współczynnik alternatywny</strong></td>
<td>Alternatywny współczynnik wartości amortyzacji.</td>
</tr>
<tr class="odd">
<td><strong>Limit kosztu</strong></td>
<td>Kwota ceny nabycia, która zostanie zaksięgowana na osobnym koncie amortyzacji niekosztowej. Kwoty do zaksięgowania na koncie amortyzacji niekosztowej są obliczane w trakcie formułowania propozycji amortyzacji, która dzieli pełne obliczenie amortyzacji na dwa wiersze:
<ul>
<li><strong>(Skorygowana) Amortyzacja</strong> — Pełna kwota amortyzacji obliczona na podstawie konfiguracji w księdze środków trwałych minus część związana z amortyzacją niekosztową (część = limit kosztu podzielony przez podstawę amortyzacji). Ta amortyzacja jest księgowana na kontach amortyzacji.</li>
<li><strong>Część niekosztowa amortyzacji</strong> - Część amortyzacji związana z limitem kosztu. Ta amortyzacja jest księgowana na kontach amortyzacji niekosztowej. Aby skonfigurować konta amortyzacji niekosztowej, wybierz kolejno opcje <strong>Środki trwałe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Profile księgowania środków trwałych</strong>, a następnie na skróconej karcie <strong>Konto księgowe</strong> wybierz opcję <strong>Amortyzacja niekosztowa</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]

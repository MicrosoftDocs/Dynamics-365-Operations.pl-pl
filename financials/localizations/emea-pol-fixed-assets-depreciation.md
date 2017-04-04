---
title: "Amortyzację środków trwałych dla Polski"
description: "Ten temat zawiera informacje o amortyzacji środków trwałych dla osób prawnych w Polsce."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBook, AssetDepreciationGroup_W, AssetParameters, AssetPosting
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 264274
ms.assetid: dcdabcbe-84e5-4615-aa39-2aa055b36da9
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 87410f0edd6aa119785b300d19996ae52ea13c13
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-assets-depreciation-for-poland"></a>Amortyzację środków trwałych dla Polski

Ten temat zawiera informacje o amortyzacji środków trwałych dla osób prawnych w Polsce.

Funkcje amortyzacji środków trwałych, które są oparte na wymagania prawne w Polsce:

-   Metody amortyzacji
-   Poziom procentu amortyzacji
-   Grupy amortyzacji
-   Tego samego dnia, co jest opcją w propozycji amortyzacji, aby wypełnić **daty** w polu wartości we wszystkich wierszach dziennika z **do tej pory** wartość, która jest zdefiniowana w propozycji amortyzacji.

## <a name="polandspecific-depreciation-methods"></a>Polandspecific metody amortyzacji
Osoby prawne w Polsce w przypadku metod amortyzacji dodatkowe, reguł i ustawień, które są używane do spełnienia wymogów rachunkowości danego środka trwałego. Zgodnie z przepisami Polski amortyzacja jest obliczana przy użyciu stawkę amortyzacji rocznej. Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md). Dostępne dla osób prawnych w Polsce są następujących metod amortyzacji:

-   **Degresywna (Polska)** – ta metoda amortyzacji uważa specjalne lokalnych przepisów prawnych o wartości środków trwałych, zmienia podczas rozpoznawania część roku obrachunkowego i kosztów. Podstawa dla tej metody amortyzacji obejmuje następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zapisz do końca
    -   Zapisz
    -   Przeszacowanie
    -   Poprzednia amortyzacja
-   **Liniowa (Polska)** — amortyzacja jest obliczana dla pierwszego okresu na podstawie liczby dni, w których użyto składnika aktywów. Na przykład jeśli środek trwały został zakupiony 15 stycznia i okres amortyzacji rozpoczyna się w dniu 1 stycznia, amortyzacja będzie obliczana dla połowie okresu. Podstawa dla tej metody amortyzacji obejmuje następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zapisz do końca
    -   Zapisz
    -   Przeszacowanie
-   **Liniowa procentowa (Polska)** -okres użytkowania jest obliczany, wprowadzając wartość procentową i podzielenie 100 procent przez wartość procentową wprowadzona. Na przykład jeśli wprowadzono 20 procent, 100 procent podzielona przez 20 procent jest 5 lat serwisu. Podstawa dla tej metody amortyzacji obejmuje następujące typy transakcji:
    -   Nabycie
    -   Korekta wartości początkowej
    -   Zapisz do końca
    -   Zapisz
    -   Przeszacowanie

Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md).

## <a name="depreciation-percent-level-parameter"></a>Parametr poziom procentu amortyzacji
Zmniejszenie salda (Polska) i prostych linii użycia metody amortyzacji wartość procentowa (Polska) **poziom procentu amortyzacji** w **ustalone parametry aktywów** strony. To pole można wybrać, jeśli poziom procentu amortyzacji powinien on z metodą amortyzacji lub pojedynczego środka trwałego do obliczania amortyzacji:

-   **Profil (standardowy)** — wybierz tę opcję, aby użyć procent z ** ** profilu amortyzacji.
-   **Księga środków trwałych** — wybierz tę opcję, aby używać tej samej metody amortyzacji. Amortyzacja będzie obliczana przy użyciu wartości procentowej w księdze środków trwałych.

## <a name="depreciation-groups"></a>Grupy amortyzacji
Osoby prawne w Polsce można połączyć grupy amortyzacji środków trwałych. Grupy amortyzacji są definiowane dla księgi środka trwałego określić szczegóły dotyczące środków trwałych, takich jak rosnący współczynnik Współczynnik alternatywny i limit kosztu. Jeśli grupa amortyzacji jest przypisany do środka trwałego, grupy amortyzacji kontroluje kwoty amortyzacji za pomocą rosnący współczynnik, przez którą mnożone jest kwota amortyzacji. Tworzenie lub edytowanie następujących grup amortyzacji na **grupy amortyzacji** strony.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Field name</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><strong>Start date</strong></td>
<td>Data, że wartość dopuszczalna Współczynnik podwyższający i koszt będzie używany.</td>
</tr>
<tr class="odd">
<td><strong>Increasing factor</strong></td>
<td>Czynnikiem, który mnoży kwotę amortyzacji. Rosnący współczynnik można skonfigurować, gdy alternatywnego profilu amortyzacji (Współczynnik alternatywny) lub profil amortyzacji dodatkowej (współczynnik dodatkowy) są używane.</td>
</tr>
<tr class="even">
<td><strong>Alternative factor</strong></td>
<td>Alternatywny współczynnik wartości amortyzacji.</td>
</tr>
<tr class="odd">
<td><strong>Cost limit</strong></td>
<td>Kwota ceny nabycia, która zostanie zaksięgowana na konto odrębne — koszt amortyzacji. Kwoty do zaksięgowania na koncie — koszt amortyzacji obliczany jest w trakcie Propozycja amortyzacji, która dzieli obliczeń Pełna amortyzacja na dwa wiersze:
<ul>
<li><strong>(Dostosowane) Amortyzacja</strong> -kwota Pełna amortyzacja obliczona na podstawie konfiguracji księgi środków trwałych minus części związanych z amortyzacji (część = limitu kosztów podzielona przez podstawa amortyzacji). Amortyzacja ta jest księgowana na kontach dla amortyzacji.</li>
<li><strong>Część niekosztowa amortyzacji</strong> - część amortyzacji związane z limitu kosztów. Amortyzacja ta jest księgowana na kontach — koszt amortyzacji. Aby skonfigurować konta — koszt amortyzacji, otwórz <strong>aktywa trwałe</strong>&gt;<strong>instalacji</strong>&gt;<strong>stałej księgowania środków trwałych</strong> profile, a następnie wybierz <strong>Amortyzacja niekosztowa</strong> w <strong>konto księgowe</strong> skróconej.</li>
</ul></td>
</tr>
</tbody>
</table>

 



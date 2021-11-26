---
title: Średnia krocząca kosztu własnego
description: Proces zamknięcia zapasów umożliwia rozliczenie transakcji wydania względem transakcji przyjęcia metodą wyceny zapasów wybranej w grupie modeli pozycji towaru. Jednak w okresie przed zamknięciem zapasów system oblicza średnią kroczącą kosztu własnego, która jest zazwyczaj używana podczas księgowania transakcji.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab90c8e57d831fbbfe0b4a6f6814ca0ab5182a7ccc0436ca5a11526b72f9da30
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781592"
---
# <a name="running-average-cost-price"></a>Średnia krocząca kosztu własnego

[!include [banner](../includes/banner.md)]

Proces zamknięcia zapasów umożliwia rozliczenie transakcji wydania względem transakcji przyjęcia metodą wyceny zapasów wybranej w grupie modeli pozycji towaru. Jednak w okresie przed zamknięciem zapasów system oblicza średnią kroczącą kosztu własnego, która jest zazwyczaj używana podczas księgowania transakcji.

System szacuje średni koszt własny towaru według następującego wzoru: 

Szacunkowa cena = (kwota fizyczna + kwota finansowa) ÷ (ilość fizyczna + ilość finansowa)

## <a name="using-the-running-average-cost-price"></a>Używanie średniej kroczącej kosztu własnego
W poniższej tabeli pokazano, kiedy transakcje magazynowe są w systemie księgowane przy użyciu średniej kroczącej kosztu własnego, a kiedy jest używany koszt własny zdefiniowany w rekordzie głównym towaru.

| Warunek                                               | System używa szacowanej średniej kroczącej kosztu własnego | System używa kosztu własnego zdefiniowanego w rekordzie głównym towaru |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Zarówno dzielna\*, jak i dzielnik\*\* są dodatnie.  | Tak                                                      | Nie                                                                |
| Dzielna\*, dzielnik\*\* lub obie te wartości są ujemne. | Nie                                                       | Tak                                                               |
| Dzielnik\*\* ma wartość 0 (zero).                        | Nie                                                       | Tak                                                               |

\* Dzielna = (kwota fizyczna + kwota finansowa) \*\* Dzielnik = (ilość fizyczna + ilość finansowa) 

**Uwaga:** Jeśli dla towaru nie zaznaczono opcji **Włącz wartość fizyczną**, system używa wartości 0 (zero) dla kwoty fizycznej i ilości fizycznej. Aby uzyskać informacje o tej opcji, zobacz [Włącz wartość fizyczną](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Zapobieganie podwyższaniu ceny
W sporadycznych przypadkach system wycenia kilka wydań, zanim zgromadzi wystarczającą liczbę przyjęć, aby mieć na czym oprzeć cenę. Taki scenariusz może spowodować sztuczne zawyżanie szacowanej średniej kroczącej kosztu własnego. Można jednak podjąć pewne kroki, aby uniknąć takiego podwyższania ceny lub złagodzić jego wpływ, kiedy nastąpi. **Scenariusz** Na towarze, któremu zaznaczono opcję **Włącz wartość fizyczną**, zostały wykonane następujące operacje:

1.  Przyjęto finansowo ilość 100 na kwotę 100,00 zł.
2.  Wydano finansowo ilość 200.
3.  Przyjęto fizycznie ilość 101 na kwotę 202,00 zł.

Podczas sprawdzania szacowanej średniej kroczącej kosztu własnego towaru oczekujesz kosztu własnego 1,51 zł. Zamiast widzisz szacowaną średnią kroczącą 102,00 zł wyliczoną na podstawie następującej formuły: szacunkowa cena = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 To podwyższenie ceny wystąpiło, ponieważ podczas finansowego wydawania 200 sztuk w kroku 2 system musi wycenić 100 sztuk, zanim odnotuje jakiekolwiek powiązane przyjęcie. Ta sytuacja powoduje ujemny poziom zapasów. Następnie system szacuje cenę jednostkową 1,00 zł, zgodnie z oczekiwaniami. Jednak gdy nadejdą towary do odnośnego przyjęcia 100 sztuk, mają one cenę jednostkową 2,00 zł. 

**Uwaga:** Mimo iż wydania powodują powstanie ujemnego stanu zapasów, stan jest dodatni podczas obliczania ceny jednostkowej. Dlatego jest używana średnia krocząca kosztu własnego, a nie cena z rekordu głównego towaru. Na tym etapie w systemie występuje przesunięcie wartości zapasów wynoszące 100,00 USD. Mimo że to księgowanie zostało wykonane dla 100 sztuk, po 1 zł dla każdej sztuki, teraz w zapasach mamy tylko jedną sztukę. Dlatego całe księgowanie przeciwstawne 100,00 zł jest przypisane tylko do jednej sztuki. Wynikiem jest sztuczne zawyżenie szacowanego kosztu własnego. 

**Uwaga:** Dla porównania warto zwrócić uwagę, że gdyby w tym scenariuszu kroki 2 i 3 zamienić miejscami, wówczas zostałoby wydanych 200 sztuk towaru z ceną jednostkową 1,51 zł oraz pozostałaby jeszcze jedna sztuka z ceną 1,51 zł. Ponieważ ten scenariusz podwyższania ceny może wystąpić w przypadku ujemnego stanu magazynowego, trudno go uniknąć w następujących sytuacjach:

-   Trzeba oszacować ceny wydania dla wartości i ilości dostępnych zapasów.
-   Trzeba skorygować wartość i ilość dostępnych zapasów w wydaniach i przyjęciach.
-   Model biznesowy dopuszcza wysyłanie lub wycenianie większej liczby sztuk towaru niż posiadane zapasy.
-   Trzeba w przyjęciu akceptować każdą wartość i ilość przysyłanych dostaw.

Jeśli jednak model biznesowy dopuszcza poniższe praktyki, mogą one pomóc uniknąć wystąpienia ujemnych ilości prowadzących do podwyższania ceny:

-   Jeśli wybierzesz opcję **Włącz wartość fizyczną** dla towaru, wyczyść pole wyboru **Ujemne wartości magazynu fizycznego** na stronie **Grupy modeli pozycji**.
-   Jeśli dla towaru *nie* zaznaczysz opcji **Włącz wartość fizyczną**, wyczyść pole wyboru **Ujemne wartości magazynu finansowego** na stronie **Grupy modeli pozycji**.

Ponadto trzeba pamiętać, że maksymalne dozwolone księgowanie przeciwstawne fizycznej wartości zapasów jest ograniczone liczbą fizycznych transakcji oraz różnicą między cenami fizycznymi i finansowymi. Gdy wszystkie transakcje fizyczne są ostatecznie aktualizowane finansowo, wartość fizyczna nie wzroście do ekstremalnego poziomu. Ponadto efekt podwyższenia znacznie się zmniejsza, gdy skumulowane księgowanie przeciwstawne jest rozłożone na wiele sztuk dostępnych zapasów, a nie tylko na jedną.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
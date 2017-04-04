---
title: "Średnia krocząca kosztu własnego"
description: "Proces zamykania magazynu rozlicza problem transakcje przychodu, oparte na metody wyceny zapasów, który wybrano w Grupa modeli towaru. Jednak przed uruchomieniem zamknięcie magazynu, system oblicza średniego kosztu, który jest zazwyczaj używany podczas księgowania transakcji rozchodów."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Średnia krocząca kosztu własnego

Proces zamykania magazynu rozlicza problem transakcje przychodu, oparte na metody wyceny zapasów, który wybrano w Grupa modeli towaru. Jednak przed uruchomieniem zamknięcie magazynu, system oblicza średniego kosztu, który jest zazwyczaj używany podczas księgowania transakcji rozchodów.

Według systemu to działa średniego kosztu własnego dla towaru przy użyciu następującego wzoru: szacunkowa cena = (kwota fizyczna + kwota finansowa) ÷ (ilość fizyczna + ilość finansowa)

## <a name="using-the-running-average-cost-price"></a>Używanie średniej kroczącej kosztu własnego
W poniższej tabeli przedstawiono, kiedy system zaksięguje transakcje magazynowe, przy użyciu średniego kosztu, a gdy używa się kosztu własnego, który jest zdefiniowany na rekord główny przedmiot w zamian.

| Warunek                                               | System używa szacowany średni koszt własny | System używa kosztu własnego, który jest zdefiniowany na wzorcu elementu |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Zarówno licznik\* i mianownik\*\* są pozytywne.  | Tak                                                      | Nr                                                                |
| Licznik\*, mianownik\*\*, lub oba są negatywne. | Nr                                                       | Tak                                                               |
| Mianownik\*\* ma wartość 0 (zero).                        | Nr                                                       | Tak                                                               |

\*Licznik = (kwota fizyczna + kwota finansowa) \*\*mianownik = (ilość fizyczna + ilość finansowa) **Uwaga:** Jeśli **Włącz wartość fizyczną** opcja nie jest zaznaczona dla towaru, system używa 0 (zero) dla fizycznej ilości i ilości fizycznej. Aby uzyskać informacje o tej opcji, zobacz [Włącz wartość fizyczną](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Zapobieganie podwyższaniu ceny
W rzadkich przypadkach system cen kilka problemów, zanim ma zbyt mało przychodów do na podstawie ceny. Taki scenariusz może spowodować sztuczne zawyżanie szacowanej średniej kroczącej kosztu własnego. Można jednak podjąć pewne kroki, aby uniknąć takiego podwyższania ceny lub złagodzić jego wpływ, kiedy nastąpi. **Scenariusz** Na towarze, któremu zaznaczono opcję **Włącz wartość fizyczną**, zostały wykonane następujące operacje:

1.  Przyjęto finansowo ilość 100 na kwotę 100,00 zł.
2.  Wydano finansowo ilość 200.
3.  Przyjęto fizycznie ilość 101 na kwotę 202,00 zł.

Podczas sprawdzania szacowanej średniej kroczącej kosztu własnego towaru oczekujesz kosztu własnego 1,51 zł. Zamiast tego możesz znaleźć szacunkowo średnia wartość z USD 102.00, która opiera się na następującym wzorze: szacunkowa cena = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 takiego wzmocnienia cenowe występuje, ponieważ 200 przedmiotów są finansowo w kroku 2, gdy system musi cena 100 elementów, zanim ma żadnych pokwitowań. Ta sytuacja powoduje ujemny poziom zapasów. System następnie oszacowania ceny jednostkowej z USD 1.00, jak możemy się spodziewać. Jednak gdy nadejdą towary do odnośnego przyjęcia 100 sztuk, mają one cenę jednostkową 2,00 zł. **Uwaga:** Mimo iż wydania powodują powstanie ujemnego stanu zapasów, stan jest dodatni podczas obliczania ceny jednostkowej. Dlatego jest używana średnia krocząca kosztu własnego, a nie cena z rekordu głównego towaru. W tym momencie system ma przesunięcia zapasów wartość USD 100.00. Mimo że to księgowanie zostało wykonane dla 100 sztuk, po 1 zł dla każdej sztuki, teraz w zapasach mamy tylko jedną sztukę. Dlatego całe księgowanie przeciwstawne 100,00 zł jest przypisane tylko do jednej sztuki. Wynikiem jest sztuczne zawyżenie szacowanego kosztu własnego. **Uwaga:** Dla porównania warto zwrócić uwagę, że gdyby w tym scenariuszu kroki 2 i 3 zamienić miejscami, wówczas zostałoby wydanych 200 sztuk towaru z ceną jednostkową 1,51 zł oraz pozostałaby jeszcze jedna sztuka z ceną 1,51 zł. Ponieważ ten scenariusz podwyższania ceny może wystąpić w przypadku ujemnego stanu magazynowego, trudno go uniknąć w następujących sytuacjach:

-   Trzeba oszacować ceny wydania dla wartości i ilości dostępnych zapasów.
-   Trzeba skorygować wartość i ilość dostępnych zapasów w wydaniach i przyjęciach.
-   Model biznesowy dopuszcza wysyłanie lub wycenianie większej liczby sztuk towaru niż posiadane zapasy.
-   Trzeba w przyjęciu akceptować każdą wartość i ilość przysyłanych dostaw.

Jeśli jednak model biznesowy dopuszcza poniższe praktyki, mogą one pomóc uniknąć wystąpienia ujemnych ilości prowadzących do podwyższania ceny:

-   Jeśli wybierzesz opcję **Włącz wartość fizyczną** dla towaru, wyczyść pole wyboru **Ujemne wartości magazynu fizycznego** na stronie **Grupy modeli pozycji**.
-   Jeśli dla towaru *nie* zaznaczysz opcji **Włącz wartość fizyczną**, wyczyść pole wyboru **Ujemne wartości magazynu finansowego** na stronie **Grupy modeli pozycji**.

Ponadto trzeba pamiętać, że maksymalne dozwolone księgowanie przeciwstawne fizycznej wartości zapasów jest ograniczone liczbą fizycznych transakcji oraz różnicą między cenami fizycznymi i finansowymi. Gdy wszystkie transakcje fizyczne są ostatecznie aktualizowane finansowo, wartość fizyczna nie wzroście do ekstremalnego poziomu. Ponadto efekt podwyższenia znacznie się zmniejsza, gdy skumulowane księgowanie przeciwstawne jest rozłożone na wiele sztuk dostępnych zapasów, a nie tylko na jedną.



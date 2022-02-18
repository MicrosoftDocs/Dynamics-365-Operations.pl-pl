---
title: Średnia krocząca kosztu własnego
description: Proces zamknięcia zapasów umożliwia rozliczenie transakcji wydania względem transakcji przyjęcia metodą wyceny zapasów wybranej w grupie modeli pozycji towaru. Jednak w okresie przed zamknięciem zapasów system oblicza średnią kroczącą kosztu własnego, która jest zazwyczaj używana podczas księgowania transakcji.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 871b3ffce45848f95d132eff3fd327295bc5084c
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092196"
---
# <a name="running-average-cost-price"></a>Średnia krocząca kosztu własnego

[!include [banner](../includes/banner.md)]

Proces zamknięcia zapasów umożliwia rozliczenie transakcji wydania względem transakcji przyjęcia metodą wyceny zapasów wybranej w grupie modeli pozycji towaru. Jednak w okresie przed zamknięciem zapasów system oblicza średnią kroczącą kosztu własnego, która jest zazwyczaj używana podczas księgowania transakcji.

System szacuje średni koszt własny towaru według następującego wzoru:

Szacunkowa cena = (kwota fizyczna + kwota finansowa) ÷ (ilość fizyczna + ilość finansowa)

## <a name="default-item-cost"></a>Domyślny koszt przedmiotu

Domyślny koszt artykułu dla wydanego produktu może być skonfigurowany na jeden z dwóch sposobów na stronie **Szczegóły wydanego produktu**:

- Utwórz koszt standardowy, wybierając **Cenę jednostki** w grupie **Ustawienia** na karcie **Zarządzanie kosztami** w panelu działania. Jeśli używasz tej metody, musisz użyć standardowej wersji rachunku kosztów, a koszt musi być aktywowany.
- Zdefiniuj domyślną cenę kosztu pozycji dla wydanego produktu, wpisując wartość w polu **Cena** na skróconej karcie **Zarządzaj kosztami**.

Oprócz wprowadzania lub tworzenia ceny możesz zaznaczyć pole wyboru **Użyj najnowszej ceny kosztowej** na skróconej karcie **Zarządzaj kosztami** na stronie **Szczegóły produktu**. W takim przypadku system automatycznie zaktualizuje pole **Cena** po zaksięgowaniu aktualizacji finansowej. Na przykład, jeśli zaksięgujesz fakturę z zamówieniem zakupu, pole to zostanie ustawione na cenę zakupu z tej faktury.

Jeśli masz cenę kosztu w aktywnej wersji kalkulacji i wprowadzasz cenę na skróconej karcie **Zarządzaj kosztami**, system użyje ceny z aktywnej wersji kalkulacji zanim użyje ceny zdefiniowanej na skróconej karcie **Zarządzaj kosztami**.

## <a name="using-the-running-average-cost-price"></a>Używanie średniej kroczącej kosztu własnego

W poniższej tabeli pokazano, kiedy transakcje magazynowe są w systemie księgowane przy użyciu średniej kroczącej kosztu własnego, a kiedy jest używany koszt własny zdefiniowany w rekordzie głównym towaru.

| Warunek | System używa szacowanej średniej kroczącej kosztu własnego | System używa domyślnej ceny kosztu elementu |
| --- | --- | --- |
| Zarówno dzielna\*, jak i dzielnik\*\* są dodatnie. | Tak | Nie |
| Dzielna\*, dzielnik\*\* lub obie te wartości są ujemne. | Nie | Tak |
| Dzielnik\*\* ma wartość 0 (zero). | Nie | Tak |

\* Dzielna = (kwota fizyczna + kwota finansowa)  
\*\*Dzielnik = (Ilość fizyczna + Ilość finansowa)

> [!NOTE]
> Jeśli dla towaru nie zaznaczono opcji **Włącz wartość fizyczną**, system używa wartości 0 (zero) dla kwoty fizycznej i ilości fizycznej. Aby uzyskać informacje o tej opcji, zobacz [Włącz wartość fizyczną](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Zapobieganie podwyższaniu ceny

W sporadycznych przypadkach system wycenia kilka wydań, zanim zgromadzi wystarczającą liczbę przyjęć, aby mieć na czym oprzeć cenę. Taki scenariusz może spowodować sztuczne zawyżanie szacowanej średniej kroczącej kosztu własnego. Można jednak podjąć pewne kroki, aby uniknąć takiego podwyższania ceny lub złagodzić jego wpływ, kiedy nastąpi.

**Scenariusz:** Na towarze, któremu zaznaczono opcję **Włącz wartość fizyczną**, zostały wykonane następujące operacje:

1. Przyjęto finansowo ilość 100 na kwotę 100,00 zł.
2. Wydano finansowo ilość 200.
3. Przyjęto fizycznie ilość 101 na kwotę 202,00 zł.

Podczas sprawdzania szacowanej średniej kroczącej kosztu własnego towaru oczekujesz kosztu własnego 1,51 zł. Zamiast tego można znaleźć szacowaną średnią bieżącą USD 102,00, która bazuje na następującej formule:

Obliczony koszt = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

To wzmocnienie wyceny ma miejsce, ponieważ kiedy 200 pozycji jest wydawanych finansowo w kroku 2, system musi wycenić 100 z nich, zanim będzie miał jakiekolwiek odpowiadające im pokwitowania. Ta sytuacja powoduje ujemny poziom zapasów. Następnie system szacuje cenę jednostkową 1,00 zł, zgodnie z oczekiwaniami. Jednak gdy nadejdą towary do odnośnego przyjęcia 100 sztuk, mają one cenę jednostkową 2,00 zł.

> [!NOTE]
> Chociaż emisje tworzą ujemne zapasy, to w momencie obliczania ceny emisyjnej zapasy są dodatnie. Dlatego jest używana średnia krocząca kosztu własnego, a nie cena z rekordu głównego towaru. Na tym etapie w systemie występuje przesunięcie wartości zapasów wynoszące 100,00 USD. Mimo że to księgowanie zostało wykonane dla 100 sztuk, po 1 zł dla każdej sztuki, teraz w zapasach mamy tylko jedną sztukę. Dlatego całe księgowanie przeciwstawne 100,00 zł jest przypisane tylko do jednej sztuki. Wynikiem jest sztuczne zawyżenie szacowanego kosztu własnego.
>
> Dla porównania zauważ, że jeśli kroki 2 i 3 zostaną odwrócone w scenariuszu, 200 sztuk zostanie wystawionych po cenie jednostkowej 1,51 USD, a jedna sztuka pozostanie po cenie jednostkowej 1,51 USD. Ponieważ ten scenariusz podwyższania ceny może wystąpić w przypadku ujemnego stanu magazynowego, trudno go uniknąć w następujących sytuacjach:
>
> - Trzeba oszacować ceny wydania dla wartości i ilości dostępnych zapasów.
> - Trzeba skorygować wartość i ilość dostępnych zapasów w wydaniach i przyjęciach.
> - Model biznesowy dopuszcza wysyłanie lub wycenianie większej liczby sztuk towaru niż posiadane zapasy.
> - Trzeba w przyjęciu akceptować każdą wartość i ilość przysyłanych dostaw.

Jeśli jednak model biznesowy dopuszcza poniższe praktyki, mogą one pomóc uniknąć wystąpienia ujemnych ilości prowadzących do podwyższania ceny:

- Jeśli wybierzesz opcję **Włącz wartość fizyczną** dla towaru, wyczyść pole wyboru **Ujemne wartości magazynu fizycznego** na stronie **Grupy modeli pozycji**.
- Jeśli dla towaru **nie** zaznaczysz opcji **Włącz wartość fizyczną**, wyczyść pole wyboru **Ujemne wartości magazynu finansowego** na stronie **Grupy modeli pozycji**.

Ponadto trzeba pamiętać, że maksymalne dozwolone księgowanie przeciwstawne fizycznej wartości zapasów jest ograniczone liczbą fizycznych transakcji oraz różnicą między cenami fizycznymi i finansowymi. Gdy wszystkie transakcje fizyczne są ostatecznie aktualizowane finansowo, wartość fizyczna nie wzroście do ekstremalnego poziomu. Ponadto efekt podwyższenia znacznie się zmniejsza, gdy skumulowane księgowanie przeciwstawne jest rozłożone na wiele sztuk dostępnych zapasów, a nie tylko na jedną.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Unikaj zerowej ceny na sprawy

Gdy opcja **Włącz wartość fizyczną** nie jest zaznaczona na stronie **Grupa modelu artykułu**, wydanie z magazynu może mieć zerową cenę nabycia, jeśli w magazynie nie ma zaktualizowanych finansowo paragonów. Aby uniknąć tego scenariusza, rozważ następujące opcje:

- Zaznacz pole **Włącz wartość fizyczną** dla towaru na stronie **Grupa modeli pozycji**. Opcja ta uniemożliwi uzyskanie zerowej ceny za wydanie, pod warunkiem, że paragon zostanie fizycznie zaktualizowany. Jeśli nie zezwolisz na ujemny stan inwentarza z natury, system obliczy średnią bieżącą z fizycznie zaktualizowanych transakcji.
- Stwórz domyślną cenę kosztu pozycji, aktywując wersję kosztorysu, która ma standardowy koszt, lub wprowadź cenę na skróconej karcie **Zarządzaj kosztami** na stronie **Szczegóły produktu**. Ta opcja jest najlepsza, gdy opcja **Włącz wartość fizyczną** nie jest wybrana na stronie **Grupy modeli przedmiotów**, ponieważ system zawsze będzie miał zapasową cenę do wykorzystania.
- Wybierz opcję **Użyj najnowszej ceny** na skróconej karcie **Zarządzaj kosztami** na stronie **Szczegóły produktu**. Ta opcja sprawi, że pole **Cena** będzie aktualne za każdym razem, gdy będziesz finansowo aktualizował paragon. Jeśli wybierzesz tę opcję, ale nie wprowadzisz domyślnej ceny lub nie aktywujesz kosztu w standardowej wersji kalkulacji kosztów, nadal możesz mieć zerowy koszt dla danej sprawy.

Jeśli masz transakcje wydania, które mają zerowy koszt, proces *Zamknięcia i korekty inwentaryzacji* skoryguje cenę kosztu poprzez utworzenie korekty po aktualizacji finansowej kwitów. Należy pamiętać, że okres finansowy, w którym następuje aktualizacja, może różnić się od okresu finansowego, w którym pozycje zostały fizycznie otrzymane lub wydane.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

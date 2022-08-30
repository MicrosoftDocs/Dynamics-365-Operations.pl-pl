---
title: Pakiety rozpoznawania przychodów
description: W tym artykule opisano funkcję pakietów dostępną w ramach modułu rozpoznawania przychodów w sekcji Rozrachunki z odbiorcami. Pakiet składa się z towaru nadrzędnego i wielu towarów składowych.
author: bking
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 9b33906fd1907ce476eec5ba36ab243aa072cf6f
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348306"
---
# <a name="revenue-recognition-bundles"></a>Pakiety rozpoznawania przychodów

[!include [banner](../includes/banner.md)]

W tym artykule opisano funkcję pakietów dostępną w ramach modułu rozpoznawania przychodów w sekcji Rozrachunki z odbiorcami. Pakiet składa się z towaru nadrzędnego i wielu towarów składowych. Towar nadrzędny jest wprowadzany w ramach zamówienia sprzedaży, dzięki czemu wprowadzanie zamówień przebiega wydajniej. Następnie jest on rozkładany na towary składowe. W dokumentach wewnętrznych, takich jak dokument dostawy, będą widniały towary składowe. W dokumentach zewnętrznych będzie jednak widoczny tylko towar nadrzędny.

> [!NOTE]
> Kanały Microsoft Dynamics 365 Commerce, takie jak kanał online, punkt sprzedaży (POS) i biura obsługi, nie obsługują rozpoznania przychodu (w tym funkcji pakietu). Obejmuje to również rozwiązanie Od prospektu do gotówki dla Dynamics 365 Supply Chain Management i Dynamics 365 Sales. Elementy skonfigurowane pod kątem użycia funkcji rozpoznawania przychodów nie powinny być dodawane do zamówień ani transakcji tworzonych w kanałach Commerce ani w rozwiązaniu Od prospektu do gotówki.

Aby skonfigurować pakiety, należy wprowadzić klucze konfiguracji dla rozpoznawania przychodów. Pakietów można jednak używać nawet w sytuacji, gdy rozpoznawanie przychodów nie zostało skonfigurowane. Analogicznie, z rozpoznawania przychodów można korzystać także w sytuacji, gdy pakiety nie zostały skonfigurowane. Jeśli rozpoznawanie przychodów zostało rozpoznane, towary składowe określają cenę przychodu i harmonogram przychodów używany do rozpoznawania przychodów lub odraczania podczas fakturowania zamówienia sprzedaży.

Konfiguracja pakietów wykorzystuje funkcję listy składowej (BOM). Aby uzyskać informacje dotyczące konfigurowania elementu pakietu, zobacz [Konfiguracja rozpoznawania przychodów](revenue-recognition-setup.md). Jeśli towar nadrzędny jest oznaczany jako pakiet, jest traktowany inaczej niż inne pozycje BOM. Poniżej znajduje się lista różnic:

- Pakiety muszą zostać rozłożone przy użyciu potwierdzenia zamówienia sprzedaży. W celu jego zastosowania należy wybrać opcję **Potwierdzanie zamówień sprzedaży** na karcie **Sprzedaż** w okienku akcji na stronie zamówienia sprzedaży. Elementów pakietu nie wolno rozkładać poprzez wybór ustawienia **Wiersz BOM** opcji **Rozłóż** menu **Wiersz zamówienia sprzedaży** na skróconej karcie **Wiersze zamówienia sprzedaży**. W przeciwnym razie dana pozycja zostanie potraktowana jako BOM, a nie jako pakiet.
- Zamówienie sprzedaży zawierające element pakietu musi zostać potwierdzone przed utworzeniem dokumentu dostawy lub faktury.
- Gdy pakiet zostaje rozłożony poprzez potwierdzenie zamówienia sprzedaży, towar nadrzędny zostaje anulowany, a cena jednostkowa i rabaty są alokowane do towarów składowych pakietu.
- Suma towarów składowych musi zawsze być równa cenie towaru nadrzędnego. W związku z tym istnieją ograniczenia dotyczące pól, które można aktualizować lub zmieniać dla towarów składowych. Nie można na przykład zmienić ręcznie ceny jednostkowej. Nie można też zmienić jej w sposób pośredni poprzez wprowadzenie w życie nowej umowy cenowej. W celu uniemożliwienia zastosowania nowej umowy cenowej zablokowano można zmiany wymiarów magazynowych towarów składowych.
- Podczas drukowania dokumentu zewnętrznego, takiego jak potwierdzenie zamówienia sprzedaży lub faktura, drukowany jest towar nadrzędny, a nie towary składowe.

## <a name="bundles-on-sales-orders"></a>Pakiety w ramach zamówień sprzedaży

Firma demonstracyjna USMF wykorzystuje następującą konfigurację pakietu. Należy zwrócić uwagę na fakt, że z elementów uwzględnionych w tym scenariuszu usunięto wszystkie ustawienia rozpoznawania przychodów, takie jak konfiguracja harmonogramów przychodów.

**Towar nadrzędny:** pakiet Laptop

- **Towar składowy:** ilość 1 towaru 1000
- **Towar składowy:** ilość 1 towaru S0021
- **Towar składowy:** ilość 1 towaru Pomoc techniczna

*Podstawowa cena sprzedaży* towarów składowych stanowi podstawowy element konfiguracji tych towarów. Podstawowa cena sprzedaży jest definiowana na skróconej karcie **Sprzedaż** towaru. Służy ona do obliczania współczynnika alokacji, gdy cena jednostkowa towaru nadrzędnego jest alokowana do towarów składowych. Ceny sprzedaży z umów handlowych nigdy nie są używane w tym celu.

Dla towarów składowych zostają zdefiniowane następujące podstawowe ceny sprzedaży:

- **1000:** 1900,00$
- **S0021:** 150,00$
- **Pomoc techniczna:** 500,00$

Zamówienie sprzedaży zostaje wprowadzone dla odbiorcy US-004, czyli firmy Cave Wholesales. Jedynym wprowadzanym wierszem jest wiersz dla elementu pakietu Laptop. Domyślna cena jednostkowa dla wiersza nadrzędnego może pochodzić z wielu miejsc, np. z umowy handlowej lub podstawowej ceny sprzedaży. W tym przykładzie jako cenę jednostkową wprowadzono ręcznie 2300$.

[![Element pakietu Laptop na zamówieniu sprzedaży.](./media/bundle-01.png)](./media/bundle-01.png)

Jako że zamówienie sprzedaży obejmuje pakiet, musi zostać potwierdzone. W oknie dialogowym potwierdzenia są wyświetlane elementy składowe pakietu.

[![Okno dialogowe Potwierdzanie zamówień sprzedaży, w którym są widoczne towary składowe.](./media/bundle-02.png)](./media/bundle-02.png)

Wydrukowany raport potwierdzenia będzie jednak zawierał tylko towar nadrzędny z pakietu, jako że raport ten jest dokumentem zewnętrznym dla odbiorcy.

[![Raport potwierdzenia zawierający jedynie towar nadrzędny.](./media/bundle-03.png)](./media/bundle-03.png)

Po potwierdzeniu zamówienia sprzedaży towar nadrzędny jest nadal wyświetlany w zamówieniu sprzedaży, ale jego stan zostaje zmieniony na **Anulowano**. Ponadto kwota netto jest śledzona w polu **Kwota netto pakietu**. Ta kwota jest wymagana w celu umożliwienia wydrukowania faktury, ponieważ na fakturze widnieje towar nadrzędny, a nie towary składowe.

Suma towarów składowych musi być równa wartości **Kwota netto pakietu** towaru nadrzędnego, ponieważ wartość ta stanowi kwotę prezentowaną odbiorcy na wydrukowanej fakturze. W celu zapewnienia, że faktura odpowiada kwotom zaksięgowanym w księdze głównej, możliwość edycji towarów składowych jest ograniczona. Nie można na przykład zmienić oddziału ani magazynu, ponieważ na podstawie umowy handlowej taka zmiana mogłaby spowodować zmianę ceny.

Cena jednostkowa z wiersza towaru nadrzędnego jest alokowana do składowych w następujący sposób:

**Suma podstawowych cen sprzedaży składowych:** 1900$ + 500$ + 150$ = 2550$

- **Składowa 1:** 2300$ × (1900 ÷ 2550) = 1713,73$
- **Składowa 2:** 2300$ × (500 ÷ 2550) = 450,98$
- **Składowa 3:** 2300$ × (150 ÷ 2550) = 135,29$

Suma składowych powinna być równa kwocie 2300$ i tak właśnie jest (1713,73$ + 450,98$ + 135,29$ = 2300$).

Jeśli są wymagane zmiany mające zastosowanie do wszystkich towarów składowych, towar nadrzędny może zostać usunięty. W takim przypadku towary składowe także zostaną usunięte. Następnie można ponownie dodać towar nadrzędny i wprowadzić wymagane zmiany przed potwierdzeniem zamówienia sprzedaży.

[![Element pakietu, który obejmuje zmiany w zakresie towarów składowych.](./media/bundle-04.png)](./media/bundle-04.png)

Gdy zamówienie sprzedaży zostanie odebrane i zapakowane, dokumenty będą zawierać tylko elementy składowe pakietu. Dokument dostawy i faktura muszą uwzględniać pełny pakiet. W przeciwnym razie nie będzie możliwe ich zaksięgowanie. Na przykład w tym oknie dialogowym wyświetlane są trzy towary składowe. W przypadku próby usunięcia jednego z nich zostanie wyświetlony komunikat o błędzie informujący, że wszystkie produkty należące do pakietu muszą zostać wysłane, aby można było je zafakturować.

Pakiet musi zostać wysłany i zafakturowany jako pełny pakiet. Jeśli na przykład ilość towaru 1000 zostanie zmieniona na 4, ale ilość innych towarów składowych pozostanie na poziomie 5, nie będzie można zafakturować dokumentu dostawy i faktury.

Częściowa wysyłka i zafakturowanie są możliwe tylko w przypadku, tylko ilość zostanie zmniejszona dla wszystkich składników pakietu. Przykład: na zamówieniu sprzedaży wprowadzona zostaje ilość 5 dla elementu pakietu Laptop. Gdy zamówienie sprzedaży zostanie potwierdzone, będą na nim widoczne trzy towary składowe, z których każdy będzie mieć przypisaną ilość 5. Domyślnie w trakcie wysyłki i fakturowania dla każdego towaru składowego zostanie ustawiona ilość 5. Można jednak dostosować ilość towarów, zmniejszając ją do 3 dla wszystkich trzech towarów składowych. W takim przypadku zostaną wysłane i zafakturowane trzy pełne pakiety. Pozostałe dwa elementy pakietu (po 2 sztuki z każdego z trzech towarów składowych) mogą zostać wysłane i zafakturowane później.

Ostatnim krokiem jest wystawienie faktury za zamówienie sprzedaży. Podczas fakturowania w oknie dialogowym faktury są wyświetlane towary składowe.

[![Okno dialogowe faktury, w którym są widoczne towary składowe.](./media/bundle-06.png)](./media/bundle-06.png)

Na wydrukowanej fakturze będzie jednak widoczny tylko towar nadrzędny.
 
[![Wydrukowana faktura zawierająca jedynie towar nadrzędny.](./media/bundle-07.png)](./media/bundle-07.png)

Arkusz faktur utworzony po zaksięgowaniu nie zawiera towaru nadrzędnego z pakietu, ponieważ towar ten ma stan **Anulowano**.

[![Arkusz faktur bez towaru nadrzędnego.](./media/bundle-08.png)](./media/bundle-08.png)

Należy pamiętać, że arkusz faktur nie zawiera towaru nadrzędnego z pakietu, ponieważ wszelkie procesy realizowane po zaksięgowaniu faktury są oparte na tym arkuszu faktur. Jeśli na przykład na karcie **Sprzedaż** w okienku akcji zostanie utworzona faktura korygująca, to będzie ona obejmować towary składowe, a nie towar nadrzędny.

[![Faktura korygująca zawierająca towary składowe, a nie towar nadrzędny.](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

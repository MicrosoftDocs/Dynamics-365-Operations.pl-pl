---
title: Ustawienia wartości parametrów wyceny
description: Po skonfigurowaniu modułu Koszty z wyładunkiem można zdefiniować zestaw wspólnych wartości, które będą dostępne po wybraniu określonych typów wartości parametrów wyceny w innych częściach aplikacji. W tym temacie wyjaśniono, jak skonfigurować te zestawy wartości.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 634635f7b751753033d1df8f56706b1e20479953
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841942"
---
# <a name="costing-parameter-values-setup"></a>Ustawienia wartości parametrów wyceny

[!include [banner](../../includes/banner.md)]

Podczas konfiguracji modułu **Koszty z wyładunkiem** można zdefiniować kilka zestawów wspólnych wartości i pokrewnych ustawień dla wartości. Wartości te będą wówczas dostępne w przypadku wybrania określonych typów wartości parametrów wyceny w innych częściach aplikacji. W tym temacie wyjaśniono, jak skonfigurować te zestawy wartości.

## <a name="set-up-cost-type-codes"></a>Ustawianie kodów typów kosztów

Kody rodzajów kosztów określają rodzaj kosztu, który jest ponoszony, gdy towary są wyładowywane do magazynu, lub koszty wyładunku podróży. Chociaż zwykle zwiększają wartość towarów, mogą one również służyć do naliczania kwot w księdze. Korekty finansowe są używane w przypadku, gdy koszt jest naliczany w czasie lub podczas serii podróży i przesunięcie w jednej transakcji.

> [!NOTE]
> Jeśli tabela typów kosztów jest współużytkowana przez firmy, plan kont musi być również współużytkowany przez firmy. W przeciwnym razie transakcje księgowania nie będą działać poprawnie.

Aby skonfigurować kody typów kosztów, przejdź do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Kody typów kosztu**. Za pomocą przycisków w okienku akcji można tworzyć nowe kody typów kosztów, edytować istniejące kody i usuwać wybrany typ kosztu.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego kodu typu kosztów.

| Pole | opis |
|---|---|
| Kod typu kosztu | Wprowadź nazwę kodu typu kosztu. |
| opis | Wprowadź opis kodu typu kosztu. |
| Użyj stawki wysyłki | Ustaw tę opcję na wartość *Tak*, jeśli do obliczenia wartości tych kosztów musi być używany kurs wymiany podróży (czasami nazywany kursem zarządzania). W takim przypadku do wymiany faktur w obcej walucie zamiast standardowego domyślnego lub spotowego kursu wymiany zostanie zastosowany kurs dostawy. |
| Kategoria raportowania | To pole ustala kategorię raportowania dla typu kosztu. Raporty można drukować według kategorii raportowania lub według typu kosztu. |
| Typ debetu | Umożliwia określenie, czy typem kosztu ma być księgowanie po stronie debetowej towaru, konta księgowego czy dostawcy. |
| Księgowanie po stronie debetowej | Jeśli w polu **Typ debetu** jest ustawione *Konto księgowe*, wybierz opis księgowania. |
| Konto debetowe | Jeśli w polu **Typ debetu** jest ustawione *Konto księgowe*, wybierz konto księgowania do użycia. |
| Typ kredytu | Wybierz, czy ten typ kosztu powinien uznawać towar, konto księgowe czy dostawcę. |
| Księgowanie po stronie kredytowej | Jeśli w polu **Typ kredytu** jest ustawione *Konto księgowe*, wybierz opis księgowania. |
| Konto kredytowe | Jeśli w polu **Typ kredytu** jest ustawione *Konto księgowe*, wybierz konto księgowania do użycia. |
| Konto rozliczeniowe | Wybierz konto rozliczeniowe dla typu kosztu. Zaleca się określenie osobnego konta rozliczeniowego dla każdego typu kosztu, aby ułatwić uzgadnianie. |
| Standardowy typ księgowania kosztów | Jeśli używasz wyceny standardowej, wybierz opis księgowania. |
| Konto odchylenia kosztów standardowych. | <p>Jeśli korzystasz z kalkulacji kosztów standardowych, konto określone w tym miejscu zostanie użyte do zaksięgowania wszelkich odchyleń. Na tym koncie jest używany podział kosztów z wyładunkiem na stronie **Ceny towaru**. Podział jest tworzony za pomocą okresowej procedury aktualizowania cen.</p><p>Na przykład standardowy koszt towaru to 15,00 USD, FOB to 13,00 USD, a fracht 2,00 USD. Po otrzymaniu faktury za zapasy, towar jest odbierany po 15,00 USD, ale występuje standardowe odchylenie ceny o 2,00 USD, ponieważ rzeczywisty FOB wynosi 13,00 USD. Odchylenie jest księgowane na koncie odchylenia cen standardowych ustawionym w profilu księgowania towarów. Ponieważ szacowany koszt frachtu wynosi 2,00 USD, nie ma odchyleń w momencie księgowania faktury magazynowej. Jednak po otrzymaniu faktury za fracht koszt frachtu wynosi 2,50 USD za sztukę. W związku z tym do podanego kosztu księgowana jest wariancja 0,50 USD. |
| Konto odchylenia średniej ruchomej | <p>Jeśli korzystasz z ruchomej średniej ceny, konto określone w tym miejscu będzie używane do księgowania wszelkich odchyleń.</p><p>Na przykład szacowany fracht to 2,00 USD. Jednak po otrzymaniu faktury za fracht koszt frachtu wynosi 2,50 USD za sztukę. W związku z tym należy zaksięgować rozbieżność 0,50 USD.</p><p>Jeśli w opcji **Księguj korekty jako odchylenie** jest ustawiona wartość *Tak* na stronie **Parametry kosztów z wyładunkiem** z oszacowanych i rzeczywistych kosztów wysyłki, wszystkie odchylenia między szacowanym a rzeczywistymi kosztami wysyłki zostaną zaksięgowane na koncie odchylenia średniej ruchomej, które jest określone w tym miejscu. Gdy opcja **Księguj korekty jako odchylenie** jest ustawiona na *Nie*, używane są standardowe funkcje, a odchylenie zostanie zastosowane do zapasów lub do konta odchylenia średniej ruchomej, które jest określone w tym miejscu, zależnie od dostępnych zapasów.</p> |
| Konto naliczania opłaty | Umożliwia wybór konta używanego do naliczania szacowanych kosztów po zaksięgowaniu faktury zakupu. To pole jest używane tylko wtedy, gdy opcja **Użyj typu kosztu konta naliczania** jest ustawiona na *Tak* na skróconej karcie **Kalkulacja kosztów** na karcie **Ogólne** na stronie **Parametry kosztu z wyładunkiem**. |
| Konto opłaty | Umożliwia wybór konta używanego do przechwytywania kosztów transportu przychodzącego, które zostały zafakturowane przez dostawcę. Kwota jest księgowana jako obciążenie. Konto przeciwstawne jest kontem odchylenia magazynu. To księgowanie daje efekt tylko jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na stronie **Parametry rozrachunków z dostawcami**. |
| Konto odchyleń | Konto, które zostanie użyte do przeciwstawne naliczenia opłat po zaksięgowaniu faktury zakupu. To pole jest używane tylko wtedy, gdy opcja **Użyj typu kosztu konta naliczania** jest ustawiona na *Tak* na skróconej karcie **Kalkulacja kosztów** na karcie **Ogólne** na stronie **Parametry kosztu z wyładunkiem**. |

## <a name="vendor-cost-type-groups"></a>Grupy typów kosztów dostawcy

Grupy typów kosztów dostawców ułatwiają określenie sposobu *automatycznego ustalania opłat za koszty* i stosowania ich w podróży. Dostawcy o podobnych kosztach importu są ze sobą powiązani. Na przykład wszyscy dostawcy z rynków nowo dostępnych płacą taką samą wartość procentową cła za ten sam typ produktu, który jest kupowany z rynku o takiej samej wartości.

Grupy typów kosztów dostawcy można obsługiwać, przechodząc do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Grupy typów kosztów dostawców**. Na stronie **Grupy typów kosztów dostawcy** jest wymieniona siatka z listą wszystkich istniejących grup typów kosztów dostawcy. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wiersze w siatce.

W poniższej tabeli opisano pola dostępne w każdym wierszu siatki.

| Pole | opis |
|---|---|
| Grupy typów kosztów dostawcy | Umożliwia wprowadzenie unikatowej nazwy grupy typów kosztów dostawcy (np. *Rynki wschodzące*). |
| opis | Wprowadź opis grupy typów kosztów dostawcy. Ten opis może zawierać szczegółowe informacje na temat poziomu lub typu opłaty skojarzonej z grupą dostawców. |

## <a name="item-cost-type-groups"></a>Grupy typów kosztów pozycji

Grupy typów kosztów pozycji ułatwiają określenie sposobu *automatycznego ustalania opłat za koszty* i stosowania ich w podróży. Podobne towary są ze sobą połączone. Na przykład wszystkie towary, dla których stawka cła wynosi 5 procent, mogą należeć do określonej grupy typów kosztów.

Grupy typów kosztów pozycji można obsługiwać, przechodząc do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Grupy typów kosztów pozycji**. Na stronie **Grupy typów kosztów pozycji** jest wymieniona siatka z listą wszystkich istniejących grup typów kosztów pozycji. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wiersze w siatce.

W poniższej tabeli opisano pola dostępne w każdym wierszu siatki.

| Pole | opis |
|---|---|
| Grupy typów kosztów pozycji | Umożliwia wprowadzenie unikatowej nazwy grupy typów kosztów pozycji (np. *Cło 5%*). |
| opis | Wprowadź opis grupy typów kosztów pozycji. Ten opis może zawierać szczegółowe informacje na temat poziomu lub typu opłaty skojarzonej z grupą pozycji. |

> [!NOTE]
> Typ kosztu towaru jest połączony z towarem za pośrednictwem pola **Grupa typów kosztów** na skróconej karcie **Zakup** na stronie **Zwolnionego produktu** pozycji.

## <a name="transfer-order-cost-type-groups"></a>Grupy typów kosztów zamówienia przeniesienia

Grupy typów kosztów zamówienia przeniesienia ułatwiają określenie sposobu *automatycznego ustalania opłat za koszty*. Podobne towary są ze sobą połączone. Na przykład wszystkie towary, dla których stawka cła wynosi 7 procent, mogą należeć do określonej grupy typów kosztów.

Grupy typów kosztów zamówienia przeniesienia można obsługiwać, przechodząc do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Grupy typów kosztów zamówienia przeniesienia**. Na stronie **Grupy typów kosztów zamówienia przeniesienia** jest wymieniona siatka z listą wszystkich istniejących grup typów kosztów zamówienia przeniesienia. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wiersze w siatce.

W poniższej tabeli opisano ustawienia dostępne w każdym wierszu siatki.

| Pole | opis |
|---|---|
| Grupy typów kosztów zamówienia przeniesienia | Umożliwia wprowadzenie unikatowej nazwy grupy typów kosztów zamówienia przeniesienia (np. *Cło 7%*). |
| opis | Wprowadź opis grupy typów kosztów zamówienia przeniesienia. Ten opis może zawierać szczegółowe informacje na temat poziomu lub typu opłaty skojarzonej z grupą kosztu zamówienia przeniesienia. |

> [!NOTE]
> Typ kosztu zamówienia przeniesienia jest połączony z towarem za pośrednictwem pola **Grupa typów kosztów zamówienia przeniesienia** na skróconej karcie **Zakup** na stronie **Zwolnionego produktu** pozycji.

## <a name="cost-templates"></a>Szablony kosztów

Funkcji tej można użyć w celu ustawienia wartości domyślnych, o których mogą nie wiedzieć użytkownicy, którzy chcą oszacować koszty. Szablony kosztów mogą pomóc zmniejszyć złożoność procesu szacowania, minimalizując wybory, które użytkownicy muszą dokonać, aby uzyskać dokładne oszacowanie.

Aby pracować z szablonami kosztów, przejdź do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Szablon kosztu**. Na stronie **Szablony kosztów** w okienku listy po lewej stronie są widać wszystkie bieżące szablony kosztów. Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania szablonów.

W poniższej tabeli przedstawiono ustawienia dostępne w nagłówku dla każdego szablonu.

| Pole | opis |
|---|---|
| Szablon kosztów | Wprowadź unikatową nazwę szablonu kosztu. Nazwa zwykle opisuje współczynnik lub mnożnik kosztu dla szablonu. |
| opis | Umożliwia wprowadzenie krótkiego opisu szablonu kosztu. |
| Firma przewozowa | Wybierz konto dostawcy firmy przewozowej do skojarzenia z szablonem kosztów. |
| Metoda dostawy | Umożliwia wybór trybu dostawy, który ma być szablon kosztów obliczany podczas obliczania szacowanego kosztu towaru. To pole pomoże określić koszty samochodów, które są powiązane z towarami w kosztorysie. |
| Typ kontenera wysyłkowego | Wybierz typ kontenera wysyłkowego, który ma być powiązany z szablonem kosztów. To pole pomoże określić koszty samochodów, które są powiązane z towarami w kosztorysie. |
| Broker urzędu celnego | Wybierz brokera celnego (dostawcę), który ma być skojarzeniu z szablonem kosztów. To pole pomaga ustalić automatyczne koszty, które są skojarzone z szacowaniem kosztów. |
| Współczynnik | Umożliwia wprowadzenie współczynnika stosowanego do ostatecznego szacowania kosztów towarów Na przykład aby dodać 10 procent do obliczonego oszacowania kosztów, wprowadź *1,10*. |

## <a name="volumetric-divisors"></a>Dzielniki objętościowe

Dzielniki wolumetryczne służą do obliczania ciężaru objętościowego. Każda firma transportowa / spedycyjna formułuje własne dzielniki wolumetryczne. Ponadto dzielniki firmy zwykle różnią się w zależności od sposobu dostawy. Na przykład przewóz lotniczy i morski często mają bardzo różne dzielniki. Firma może również skomplikować swoje zasady, w zależności od tego, skąd wysyła.

Na przykład paczka wysyłana samolotem ma objętość 3 metrów sześciennych (m³). Firma pobiera opłaty według wagi wolumetrycznej i stosuje dzielnik wolumetryczny równy 6. Ten dzielnik jest mnożony przez objętość, aby określić wagę wolumetryczną. Dlatego masa wolumetryczna w tym przykładzie wynosi 3 × 6 = 18 kilogramów (kg).

Aby ustawić dzielniki wolumetryczne, przejdź do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Dzielniki wolumetryczne**. Strona **Dzielniki wolumetryczne** zawiera siatkę, w która zawiera listę wszystkich istniejących dzielników wolumetrycznych. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wiersze w siatce.

W poniższej tabeli opisano pola dostępne w każdym wierszu siatki.

| Pole | opis |
|---|---|
| Firma przewozowa | Wybierz konto dostawcy firmy przewozowej, które jest skojarzone z dzielnikiem wolumetrycznym. |
| Kod typu kosztu | Umożliwia wybór kodu typu kosztu skojarzonego z dzielnikiem wolumetrycznym. W tym polu można umieszczać typy kosztów w przedziałach raportowania. Raporty można drukować według kategorii raportowania lub według typu kosztu. |
| Port źródłowy | Wybierz port „od”, do którego ma zastosowanie dzielnik wolumetryczny. |
| Dzielnik objętościowy | Wprowadź wartość dzielnika wolumetrycznego, która ma zastosowanie do wiersza. W celu określenia wagi objętościowej paczki w wolumetryka zostanie *pomnożona* przez objętość każdej paczki. |

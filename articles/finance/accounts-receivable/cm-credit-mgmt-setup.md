---
title: Ustawienia parametrów modułu Zarządzanie kredytami
description: W tym temacie opisano opcje, których można wykorzystać w celu skonfigurowania zarządzania kredytami w celu spełnienia wymagań firmy.
author: JodiChristiansen
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 768fb5121ae6be513c4a533a20027cf784640b2a
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753472"
---
# <a name="credit-management-parameters-setup"></a>Ustawienia parametrów modułu Zarządzanie kredytami

[!include [banner](../includes/banner.md)]

W tym temacie opisano opcje, których można wykorzystać w celu skonfigurowania zarządzania kredytami w celu spełnienia wymagań firmy. Aby rozpocząć korzystanie z funkcji zarządzania kredytami, należy skonfigurować parametry na stronie **Parametry modułu Kredyt i windykacje** (**Kredyt i windykacje \> Konfiguracja \> Parametry modułu Kredyt i windykacje**).

## <a name="credit-parameters"></a>Parametry kredytu

Istnieją cztery karty skrócone w sekcji **Kredyt**, w których można zmienić parametry kontrolujące zarządzanie kredytami: **Wstrzymania kredytu**, **Punkt kontrolnyzarządzania kredytami**, **Statystyki zarządzania kredytami** oraz **Limity kredytu**. W poniższych sekcjach opisano ustawienia dostępne na poszczególnych skróconych kartach.

### <a name="credit-holds"></a>Wstrzymania kredytu

- Ustawienie **Zezwalaj na edycję zamówień sprzedaży po zwolnieniu wstrzymania** do wartości **Nie** spowoduje ponowne sprawdzenie reguł księgowania, jeśli wartość zamówienia sprzedaży (cena rozszerzona) wzrosła, ponieważ zamówienie sprzedaży zostało zwolnione z listy zablokowanych. ,
- W polu **Przyczyny anulowania zamówień** wybierz przyczynę zwolnienia, która będzie używana domyślnie w przypadku anulowania zamówienia sprzedaży, które było w dniu wstrzymania zarządzania kredytem.
- Ustawienie opcji **Sprawdź limit kredytu dla grupy odbiorców kredytu** na wartość **Tak** powoduje sprawdzenie limitu kredytu grupy odbiorców kredytu, gdy odbiorca zamówienia sprzedaży należy do grupy odbiorców kredytu. Limit kredytu dla grupy zostanie sprawdzony, a następnie, jeśli jest wystarczający, zostanie sprawdzony limit kredytu dla odbiorcy.
- Ustawienie opcji **Sprawdź limit kredytu, jeśli warunki płatności zostaną zwiększone** do wartości **Tak**, aby sprawdzić, czy warunki płatności w zamówieniu sprzedaży różnią się od domyślnych warunków płatności dla odbiorcy. Jeśli nowe warunki płatności mają wyższą rangę niż pierwotne warunki płatności, zamówienie jest umieszczane w wstrzymaniu zarządzania kredytami.
- Ustawienie opcji **Sprawdź limit kredytu, jeśli rabat rozliczeniowy zostanie zwiększony** do wartości **Tak** w celu sprawdzenia rankingu rabatów rozliczeniowych w celu ustalenia, czy rabat gotówkowy w zamówieniu sprzedaży różni się od domyślnego rabatu gotówkowego dla odbiorcy. Jeśli nowy rabat gotówkowy ma wyższą rangę niż pierwotny rabat gotówkowy, zamówienie zostaje wstrzymane w zarządzaniu kredytem.
- W polu **przyczyna zwolnienia zmodyfikowanych zamówień** wybierz przyczynę wydania, która będzie używana domyślnie, gdy zmodyfikowane zamówienia są automatycznie zwalniane z wstrzymania zarządzania kredytami.
- Ustaw **Ignoruj regułę blokowania wygasłego limitu kredytowego, gdy data wygaśnięcia jest pusta** opcję na **tak**, aby kontrolować zasadę **Wygasł limit kredytu**. Ustawienie opcji na **nie** powoduje zablokowanie zamówienia, gdy data ważności jest pusta.
- W module Zarządzanie magazynem ładunki mogą być tworzone w momencie wprowadzania zamówienia sprzedaży. Ustawienie opcji **Usuń zablokowane wiersze** ładunku na wartość **nie** powoduje pozostawienia wierszy zamówienia sprzedaży w ładunku, gdy zamówienie sprzedaży ma wstrzymany kredyt. Nie można przetworzyć ładunku, dopóki zamówienie sprzedaży jest wstrzymane. Ustaw opcję na **Tak**, aby usunąć wiersze zamówienia sprzedaży z obciążenia, gdy zamówienie sprzedaży jest wstrzymane. Następnie można przetworzyć ładunek.
- Zamówienia sprzedaży mogą być automatycznie zwalniane z przeglądu zarządzania kredytami. W polu **Przyczyna zwolnienia automatycznego** wybierz przyczynę wydania, która będzie używana domyślnie podczas automatycznego zwalniania zamówień sprzedaży.
- Zamówienia sprzedaży mogą być automatycznie zwalniane z przeglądu zarządzania kredytami. W polu **Automatyczne zwalnianie** wybierz opcję **Bez księgowania**, aby zwolnić wstrzymanie zamówienia. Należy ręcznie uruchomić proces, który wstrzymał zamówienie. Wybierz opcję **przy księgowaniu** do zaksięgowania zamówienia przy użyciu tego samego procesu księgowania, który został uruchomiony, gdy zamówienie sprzedaży zostało wstrzymane.

### <a name="credit-management-checkpoint"></a>Punkt kontrolny zarządzania kredytem

Można określić chronometraż używany do sprawdzania zamówień sprzedaży dla rozchodów kredytowych. Na skróconej karcie **Punkt kontrolny zarządzania kredytami** określa procesy księgowania dokumentów, które obejmują przetwarzanie reguł zarządzania kredytami. Reguły kredytowe można również sprawdzać podczas księgowania pro-forma lub pełnego zaksięgowania zamówienia sprzedaży. Zaznacz pola wyboru, aby zdefiniować procesy księgowania, które powinny wstrzymać zamówienie, jeśli zostanie wykryty błąd po przetworzeniu reguł blokowania zarządzania kredytami.

Można również zdefiniować liczbę dni prolongaty przed ponownym sprawdzeniem reguł kredytu. Mimo że reguły zarządzania kredytami można określić przy księgowaniu, reguły nie będą sprawdzane w odniesieniu do określonej liczby dni prolongaty. Na przykład można potwierdzić zamówienie sprzedaży w dniu 1., a następnie określić dwa dni prolongaty dla kroku potwierdzenia. W takim przypadku reguły kredytowe nie będą sprawdzane w kolejnym kroku księgowania (na przykład: Utworzenie dokumentu dostawy lub zafakturowanie zamówienia) do dnia 4. Po dniu 4 lub później po zaksięgowaniu zostaną ponownie sprawdzone reguły, a liczba dni prolongaty zostanie zmieniona na wartość określoną dla następnego punktu kontrolnego księgowania.

Jeśli liczba dni prolongaty nie zostanie określona, reguły kredytu będą sprawdzane przy każdym kroku księgowania skonfigurowanym do uruchamiania reguł zarządzania kredytami. Jeśli zamówienie sprzedaży zostanie zwolnione bez księgowania, a następnie ponownie uruchomiony ten sam krok przetwarzania zamówienia, reguły kredytu zostaną ponownie sprawdzone. Zamówienie jest na przykład wstrzymywane po potwierdzeniu, a zwolnienie jest możliwe przy księgowaniu lub bez niego. W takim przypadku zamówienie zostanie wstrzymane ponownie, jeśli zostanie ponownie potwierdzone. Należy używać dni prolongaty, jeśli zamówienie powinno zostać przeniesione do następnego kroku przetwarzania bez konieczności ponownego przetrzymywania.

Nie można określić dni prolongaty dla niektórych punktów kontrolnych księgowania, ale nie dla innych. Należy skonfigurować wszystkie punkty kontrolne księgowania, tak aby miały dni prolongaty, lub skonfigurować je w taki sposób, aby nie miały dni prolongaty.

- Zaznaczenie pola wyboru **Księgowanie** powoduje uruchomienie reguł zarządzania kredytami po uruchomieniu punktu kontrolnego księgowania wyświetlanego w wierszu. Jeśli pole wyboru nie zostanie zaznaczone, reguły będą sprawdzane tylko raz w całym procesie księgowania.
- W przypadku zaznaczenia pola wyboru **Księgowanie** należy określić liczbę dni prolongaty, które powinny upłynąć przed ponownym sprawdzeniem reguł blokowania. Nie można dodać dni prolongaty, jeśli pole wyboru **Księgowanie** jest puste.
- Zaznaczenie pola wyboru **Pro forma** powoduje uruchomienie reguł zarządzania kredytami po uruchomieniu punktu kontrolnego pro-forma wyświetlanego w wierszu. W większości przypadków pole **Księgowanie** jest ustawiane na wartość **nie** w oknie dialogowym, które pojawia się podczas księgowania zamówienia sprzedaży.
- W przypadku zaznaczenia pola wyboru **Księgowanie** należy określić liczbę dni prolongaty, które powinny upłynąć przed ponownym sprawdzeniem reguł blokowania. Nie można dodać dni prolongaty, jeśli pole wyboru **Księgowanie** jest puste.

### <a name="credit-management-statistics"></a>Statystyki zarządzania kredytem

W polu informacji **Statystyki zarządzania kredytami odbiorców** znajduje się kilka statystyk zarządzania kredytami, które znajdują się na stronie **Odbiorca**. Należy określić kilka wartości wymaganych do obliczenia tych statystyk. Umożliwia wprowadzenie liczby miesięcy używanej do obliczania następujących wartości w polu informacji **Statystyki zarządzania kredytami odbiorców**:

1. Wskaźnik rotacji należności w dniach 1
2. Wskaźnik rotacji należności w dniach 2
3. Średnie saldo 1
4. Średnie saldo 2
5. Średni limit kredytu %
6. Średni poziom ekspozycji %

### <a name="credit-limits"></a>Limity kredytu

- W module zarządzania kredytem limit kredytu odbiorcy jest pokazywany w walucie odbiorcy. Należy zdefiniować typ kursu wymiany dla limitu kredytu w walucie odbiorcy. W polu **Typ kursu wymiany limitu kredytu** wybierz typ kursu wymiany, który ma zostać użyty do przekonwertowania podstawowego limitu kredytu na limit kredytu odbiorcy.
- Ustawienie opcji **Zezwalaj na ręczne edytowanie limitów kredytu** na wartość **nie** powoduje, że użytkownicy nie będą mogli edytować limitów kredytowych na stronie **Odbiorcy**. Jeśli ta opcja jest ustawiona na wartość **nie**, zmiany w limicie kredytu odbiorcy mogą być wprowadzane tylko przez księgowanie transakcji korekty limitu kredytu.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Parametry sekwencji numerów i współużytkowanej sekwencji numerów

Identyfikator arkusza jest wymagany do przetwarzania korekt limitu kredytu. Należy dodać numer korekty limitu kredytu, który ma być użyty do wygenerowania identyfikatora arkusza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

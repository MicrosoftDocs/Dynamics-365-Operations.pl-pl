---
title: Horyzonty czasowe zapotrzebowania
description: W tym temacie opisano sposób skonfigurowania horyzontów czasowych zapotrzebowania w przypadku korzystania z optymalizacji planowania. Horyzont czasowy zapotrzebowania wskazuje horyzont i limit planowania.
author: ChristianRytt
manager: tfehr
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f970d7aa9f758d3bc35b7a1b9d1e43be928fd250
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033226"
---
# <a name="coverage-time-fences"></a>Horyzonty czasowe zapotrzebowania

W tym temacie opisano sposób skonfigurowania *horyzontów czasowych zapotrzebowania* w przypadku korzystania z optymalizacji planowania. Planiści mogą definiować horyzont planowania (horyzont czasowy zapotrzebowania w dniach) oraz wykluczyć podaż i popyt wykraczający poza ten horyzont. Dlatego też za pomocą horyzontów czasowych zapotrzebowania można zapobiec „hałasowi”, który jest spowodowany sugestiami podaży, których nie trzeba zaksięgować przez wiele miesięcy. Przykłady to prognozy na następny rok i zamówienia klientów, które są poza zwykłym czasem realizacji.

Horyzont czasowy zapotrzebowania to liczba dni po dacie dzisiejszej (lub dokładniej: dacie uruchomienia planowania), w których podaż i popyt są wykluczone. Aby uniknąć opóźnień, należy upewnić się, że ten horyzont czasowy zapotrzebowania jest dłuższy niż łączny czas realizacji. Domyślna wartość systemowa to 100 dni.

Horyzont czasowy zapotrzebowania można określić na każdym z następujących poziomów:

- **Grupa zapotrzebowania** — dla każdej grupy zapotrzebowania można ustawić domyślny horyzont czasowy zapotrzebowania.
- **Zapotrzebowanie na towar** — można zastąpić horyzont czasowy zapotrzebowania, który jest dziedziczony z grupy zapotrzebowania przypisanej do pozycji.
- **Plan główny** — można zastąpić horyzonty czasowe zapotrzebowania, który są dziedziczone z ustawień grupy zapotrzebowania i zapotrzebowania na pozycję.

Poniższe sekcje zawierają informacje dotyczące określania grupy zapotrzebowania na każdym poziomie.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Ustawianie horyzontu czasowego zapotrzebowania dla grupy zapotrzebowania

Po określeniu horyzontu czasowego zapotrzebowania dla grupy zapotrzebowania ustawienie dotyczy wszystkich pozycji (produktów) należących do tej grupy. Ustawienie to można jednak zastąpić dla określonych towarów lub określonych planów głównych.

Aby określić horyzont czasowy zapotrzebowania dla grupy zapotrzebowania, należy wykonać następujące czynności.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Grupy zapotrzebowania**.
1. Wybierz istniejącą grupę zapotrzebowania z listy lub utwórz nową grupę zapotrzebowania.
1. Na skróconej karcie **Ogólne** ustaw w polu **Horyzont czasowy zapotrzebowania (dni)** liczbę dni, która ma być używana jako horyzont czasowy zapotrzebowania dla grupy zapotrzebowania.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Ustawianie horyzontu czasowego zapotrzebowania dla określonej pozycji

Każda pozycja (produkt) należy do grupy zapotrzebowania. Jeśli żadna grupa zapotrzebowania nie jest jawnie przypisana do pozycji, obowiązuje domyślna grupa zapotrzebowania. Każda pozycja dziedziczy horyzont czasowy zapotrzebowania z grupy zapotrzebowania. W razie potrzeby można jednak zastąpić ten okres dla określonych pozycji.

Aby określić horyzont czasowy zapotrzebowania dla określonej pozycji, należy wykonać następujące czynności.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt w siatce.
1. W okienku akcji na karcie **Plan** kliknij w grupie **Zapotrzebowanie** wybierz opcję **Zapotrzebowanie na pozycje**.
1. Na stronie **Zapotrzebowanie na pozycję** na karcie **Przegląd** zaznacz lub utwórz wiersz dla lokacji, w której ma zostać ustawiony horyzont czasowy zapotrzebowania.
1. Wybierz kartę **Ogólne**, aby otworzyć ustawienia dla wybranej lokacji.
1. Zaznacz pole wyboru **Ustawienia zastępowania grupy zapotrzebowania**.
1. Ustaw w polu **Horyzont czasowy zapotrzebowania (dni)** liczbę dni, która ma być używana jako horyzont czasowy zapotrzebowania dla pozycji.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Ustawianie horyzontu czasowego zapotrzebowania dla określonego planu głównego

Horyzont czasowy zapotrzebowania można określić na poziomie planu głównego. W ten sposób można zdefiniować liczbę dni, które obejmuje obliczenie planowania głównego dla planu głównego. To ustawienie zastępuje wszelkie ustawienia czasu zapotrzebowania zdefiniowane dla poszczególnych pozycji i grup zapotrzebowania.

Aby określić horyzont czasowy zapotrzebowania dla określonego plany głównego, należy wykonać następujące czynności.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz istniejący plan główny z listy lub utwórz nowy plan główny.
1. Na skróconej karcie **Horyzont czasowy zapotrzebowania (dni)** ustaw opcję **Zapotrzebowanie** na *Tak*. Następnie w polu opcji wprowadź liczbę dni, która ma być używana jako horyzont czasowy zapotrzebowania dla planu głównego.

## <a name="considerations-for-coverage-time-fences"></a>Uwagi dotyczące horyzontów czasowych zapotrzebowania

Podczas konfigurowania horyzontów czasowych zapotrzebowania należy uwzględnić następujące kwestie:

- Horyzonty czasowe zapotrzebowania wpływają tylko na dane wejściowe dla planowania głównego. Jeśli wystąpią opóźnienia, wynikające z tych zamówień planowane zamówienia mogą mieć datę późniejszą niż dzisiejsza data plus ten horyzont czasowy.
- Horyzont czasowy zapotrzebowania jest określony w dniach kalendarzowych. Kalendarze, w których są dni robocze, nie wpływają na obliczanie horyzontu czasowego zapotrzebowania. Na przykład tydzień jest zawsze traktowany jako siedem dni, nawet jeśli weekendy są ustawione jako zamknięte dni w kalendarzu czasu pracy.
- Transakcje zapotrzebowania nie będą generowane dla żadnej podaży i popytu, który przypada poza horyzontem czasowym zapotrzebowania.
- Jeśli zatwierdzona podaż i popyt przypada poza horyzontem czasowym zapotrzebowania, nie zostaną one załadowane do aparatu. W związku z tym uzupełnianie zapasów nie będzie wyzwalane, a opóźnienia nie zostaną obliczone. Mimo tego ta podaż i popyt nie powinny być usuwane z systemu.
- Odchylenia ilości zapasów bezpieczeństwa (od kluczy minimalnych) będą ignorowane, jeśli będą znajdować się poza horyzontem czasowym zapotrzebowania.
- Popyt międzyfirmowy będzie ignorowany, jeśli obliczona żądana data wysyłki nie znajduje się w granicach horyzontu czasowego zapotrzebowania. Należy zauważyć, że dla wbudowanego planowania głównego popyt międzyfirmowy nie jest ograniczony przez horyzont czasowy zapotrzebowania.
- Prognozy popytu będą ignorowane, jeśli data budżetu nie znajduje się w granicach horyzontu czasowego zapotrzebowania. Należy zauważyć, że dla wbudowanego planowania głównego prognozy popytu nie są ograniczone przez horyzont czasowy zapotrzebowania.
- Optymalizacja planowania jest powiązana ze strefą czasową. Uwzględnia ona strefę czasową w lokacjach podaży i popytu oraz dla czasu uruchomienia planowania. Na przykład planowanie główne jest wyzwalane o 11:00 15 października z lokacji w Danii (strefa czasowa GMT+1) i jest używany horyzont czasowy zapotrzebowania o długości dziesięciu dni. W tym przypadku podaż i popyt z lokacji w Seattle (strefa czasowa GMT-8) są uwzględniane do godziny 2:00 w dniu 25 października (= dziesięć 24-godzinnych dni po wyzwoleniu planowania głównego minus różnica stref czasowych, czyli 9 godzin). Należy zwrócić uwagę, że wbudowany aparat planowania głównego uwzględnia tylko datę z horyzontu czasowego zapotrzebowania. Z tego względu można uzyskiwać różne wyniki.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
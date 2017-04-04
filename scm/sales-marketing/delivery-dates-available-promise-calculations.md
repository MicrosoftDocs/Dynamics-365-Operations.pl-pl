---
title: "Zobowiązanie do zamówienia"
description: "Ten artykuł zawiera informacje o zobowiązaniach zamówień. Zobowiązania zamówień pomagają wiarygodnie deklarować daty dostawy odbiorcom oraz wprowadzają elastyczność umożliwiającą dotrzymanie tych terminów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8aa0a58b03ee18e42ca7770ea3e22311c1ddba67
ms.lasthandoff: 03/31/2017


---

# <a name="order-promising"></a>Zobowiązanie do zamówienia

Ten artykuł zawiera informacje o zobowiązaniach zamówień. Zobowiązania zamówień pomagają wiarygodnie deklarować daty dostawy odbiorcom oraz wprowadzają elastyczność umożliwiającą dotrzymanie tych terminów.

Zobowiązanie zamówienia oblicza najwcześniejsze daty wysyłki i przyjęcia, i opiera się na metodzie kontroli daty dostawy i dni transportu. Dostępne są cztery metody kontroli daty dostawy:

-   **Czas realizacji sprzedaży** -sprzedaży czasu realizacji jest czas między tworzenia zamówienia sprzedaży i wydania zapasów. Obliczanie daty dostawy opiera się na domyślnej liczby dni, a nie należy wziąć pod uwagę dostępność, znanych zapotrzebowaniem lub pokryciem planowane.
-   **ATP (dostępne ilość)** – ATP jest ilość towaru, która jest dostępna i może być zobowiązał się do klienta w określonym dniu. Obliczanie ATP obejmuje niezatwierdzone zapasy, czasy realizacji, planowane przychody i rozchody.
-   **ATP + Zapas czasu dla rozchodu** — data wysyłki jest równa dacie ATP plus zapas czasu dla rozchodu w odniesieniu do towaru. Jest to czas potrzebny na przygotowanie towaru do wysyłki.
-   **CTP (stan zapasów)** — dostępność jest obliczana na podstawie rozłożenia.

## <a name="atp-calculations"></a>Obliczenia ATP
Ilość ATP jest obliczana przy użyciu metody "ATP zbiorczej z wyprzedzeniem". Główną zaletą tej metody obliczania ATP jest, że może obsługiwać przypadkach, gdy Suma rozchodów wśród przychodów jest więcej niż najnowsze potwierdzenia (na przykład, gdy ilość z wcześniejszej daty otrzymania musi służyć do spełnienia wymogu). Metoda obliczania "ATP zbiorczej z wyprzedzeniem" zawiera wszystkie wydania, dopóki skumulowana ilość do wydania przekracza ilość skumulowana do odbierania. Z tego względu metoda obliczania ATP ocenia, czy niektóre ilości z poprzedniego okresu mogą być używane w późniejszym okresie.  

Ilość ATP jest niezatwierdzonym saldem magazynowym w pierwszym okresie. Zazwyczaj jest ona obliczana dla każdego okresu, w którym planowany jest przychód. Program oblicza okres ATP w dniach i oblicza bieżąca datę jako pierwszą datę dla ilości ATP. W pierwszym okresie ATP obejmuje dostępne zapasy ATP z potrąceniem zamówień odbiorców, które są należne lub zaległe.  

ATP są obliczane za pomocą następującego wzoru:  

ATP = ATP dla poprzedniego okresu + przyjęć dla ilości rozchodu netto bieżącego okresu — problemy dla bieżącego okresu — dla każdego okresu przyszłego dopiero w okresie, kiedy Suma przychodów dla wszystkich przyszłych okresów, do i włącznie z przyszłego okresu przekracza sumę problemów do i włącznie z przyszłym okresie.  

Jeśli nie ma już rozchodów lub przychodów do uwzględnienia, ilość ATP dla następujących dat jest taka sama jak ostatnia obliczona ilość ATP.  

Jeśli wszystkie wymiary użyte dla towaru nie zostaną podane w momencie gdy następuje sprawdzenie ATP, nadal będzie można je określić dla rozchodów i przychodów. W takim przypadku w obliczeniu ATP przychody i rozchody muszą zostać zespolone do istniejących wymiarów, aby ograniczyć liczbę wierszy rozchodów i przychodów używanych w obliczaniu ATP.  

Wyświetlana ilość ATP jest zawsze większa lub równa 0 (zero). Jeśli obliczenie da ujemną ilość ATP (na przykład, jeśli wcześniej zarezerwowana ilość przekracza dostępną ilość), program automatycznie ustawi ilość jako **0**.

### <a name="example"></a>Przykład

Pole **Horyzont czasowy wstecz dla popytu ATP** kontroluje, jak daleko wstecz na osi czasu mają być wyszukiwane opóźnione zamówienia popytowe lub rozchody towarów. Pole **Horyzont czasowy wstecz dla podaży ATP** kontroluje, jak daleko wstecz na osi czasu mają być wyszukiwane opóźnione zamówienia podażowe lub przyjęcia towarów. Na przykład, jeśli zamówienia, które są opóźnione tylko o siedem dni powinny być uwzględniane w obliczeniu ATP, oba pola powinny mieć wartość **7**.  

Pola **Przesunięcie czasowe opóźnionego popytu ATP** i **Przesunięcie czasowe opóźnionej podaży ATP** kontrolują, kiedy opóźniony popyt lub podaż mają być uwzględniane w obliczeniach ATP. Na przykład, jeśli opóźnione popyt i podać mają być uwzględniany w obliczeniach ATP pojutrze, w obu polach powinna być wartość **2**. Wartość **2** oznacza, że ilość towaru na opóźnionym zamówieniu zakupu, która powinna być uwzględniona w obliczeniu ATP, będzie widoczna jako dostępna dwa dni po dacie bieżącej.  

W następującym przykładzie pola **Horyzont czasowy wstecz dla popytu ATP** i **Horyzont czasowy wstecz dla podaży ATP** otrzymują wartość **7**, a pola **Przesunięcie czasowe opóźnionego popytu ATP** i **Przesunięcie czasowe opóźnionego popytu ATP** otrzymują wartość **1**.  

Zamówienie zakupu na 200 sztuk produktu, które powinny zostać dostarczone trzy dni temu, jeszcze nie zostało zrealizowane. W związku z tym wiersz zamówienia sprzedaży na 75 sztuk tego samego produktu, który powinien był zostać wysłany wczoraj, nie został wysłany.  

Klient dzwoni i chce zamówić 150 sztuk tego samego produktu. Gdy sprawdzasz dostępność produktu, okazuje się, że inne zamówienie zakupu na 100 sztuk tego produktu zostanie dostarczone 10 dni później.  

Tworzysz wiersz zamówienia sprzedaży dla produktu i wprowadzasz ilość **150**.  

Ponieważ metodą kontroli daty dostawy jest ATP, obliczana jest data ATP, aby ustalić najwcześniejszą możliwą datę wysyłki. Na podstawie ustawień, zamówienia zakupu opóźnione i zamówienia sprzedaży są uważane za, a wynikowa ilość ATP dla bieżącej daty jest równa 0. Jutro, gdy zamówienia zakupu opóźnione oczekuje się być odbierane, ilość ATP jest obliczana jako więcej niż 0 (w tym przypadku to jest obliczana jako 125). Jednak 10 dni od teraz, gdy oczekuje zamówienie zakupu dodatkowych 100 sztuk ma być otrzymana, ilość ATP staje się ponad 150.  

W związku z tym data wysyłki jest ustawiony na 10 dni od teraz, oparte na obliczenie ATP. Teraz można powiedzieć odbiorcy, że żądana ilość towaru może zostać dostarczona 10 dni od teraz.



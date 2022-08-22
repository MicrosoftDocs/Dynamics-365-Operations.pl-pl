---
title: Zobowiązanie do zamówienia
description: Ten artykuł zawiera informacje o zobowiązaniach zamówień. Zobowiązania zamówień pomagają wiarygodnie deklarować daty dostawy odbiorcom oraz wprowadzają elastyczność umożliwiającą dotrzymanie tych terminów.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228275"
---
# <a name="order-promising"></a>Zobowiązanie do zamówienia

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o zobowiązaniach zamówień. Zobowiązania zamówień pomagają wiarygodnie deklarować daty dostawy odbiorcom oraz wprowadzają elastyczność umożliwiającą dotrzymanie tych terminów.

Zobowiązanie zamówienia oblicza najwcześniejsze daty wysyłki i przyjęcia, i opiera się na metodzie kontroli daty dostawy i dni transportu. Możesz wybrać spośród następujących metod kontroli daty dostawy:

- **Czas realizacji sprzedaży** — Czas realizacji sprzedaży to okres od utworzenia zamówienia sprzedaży do wysyłki towarów. Obliczenie daty dostawy opiera się na domyślne liczbie dni i nie uwzględnia dostępności zapasu, znanego popytu ani planowanej podaży.
- **ATP (dostępność zapasów)** — ATP to dostępna ilość towaru, która może zostać zarezerwowana dla odbiorcy na konkretny dzień. Obliczanie ATP obejmuje niezatwierdzone zapasy, czasy realizacji, planowane przychody i rozchody.
- **ATP + Zapas czasu dla rozchodu** — data wysyłki jest równa dacie ATP plus zapas czasu dla rozchodu w odniesieniu do towaru. Jest to czas potrzebny na przygotowanie towaru do wysyłki.
- **CTP (stan zapasów)** — dostępność jest obliczana na podstawie rozłożenia. Jeśli używasz optymalizacji planowania, *metoda kontroli daty dostawy CTP* jest niedozwolone i jeśli jest zaznaczona, spowoduje błąd podczas wykonywania obliczeń. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania funkcji CTP, zobacz [Oblicz daty dostawy zamówień sprzedaży za pomocą CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP dla optymalizacji planowania** — użyj obliczenia CTP dostarczanego przez optymalizację planowania. Ta opcja nie ma wpływu, jeśli używasz wbudowanego głównego aparatu planowania. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania funkcji CTP, zobacz [Oblicz daty dostawy zamówień sprzedaży za pomocą CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Po zaktualizowaniu zamówienia sprzedaży informacje o obietnicach zamówienia są aktualizowane tylko wtedy, gdy nie można spełnić istniejącej daty obietnicy zamówienia, co ilustruje poniższy przykład:
>
> - **Przykład 1** : bieżąca data obietnicy zamówienia wynosi 20 lipca, ale z powodu zwiększonej ilości nie będzie można jej dostarczyć do 25 lipca. Ponieważ data bieżąca nie może być już spełniona, obietnice zamówień są uruchamiane.
> - **Przykład 2**: bieżąca data obietnicy zamówienia wynosi 20 lipca, ale z powodu zmniejszonej ilości będzie można ją dostarczyć do 15 lipca. Ponieważ jednak w dalszym ciągu można zrealizować bieżącą datę, obietnica zamówienia nie zostanie uruchomiona, a 20 lipca pozostaje datą obietnicy zamówienia.

## <a name="atp-calculations"></a>Obliczenia ATP

Ilość ATP jest obliczana na podstawie metody „zbiorcze ATP z wyprzedzeniem”. Główną zaletą tej metody obliczania ATP jest to, że może ona obsługiwać przypadki, gdzie suma wydań między przyjęciami jest większa niż ostatnie przyjęcie (np. gdy wystąpi potrzeba użycia ilości z wcześniejszego przyjęcia, aby zaspokoić określone zapotrzebowanie). Metoda obliczania „zbiorcze ATP z wyprzedzeniem” obejmuje wszystkie wydania do momentu, aż łączna ilość do przyjęcia będzie większa niż łączna ilość do wydania. Z tego względu metoda obliczania ATP ocenia, czy niektóre ilości z poprzedniego okresu mogą być używane w późniejszym okresie.

Ilość ATP jest niezatwierdzonym saldem magazynowym w pierwszym okresie. Zazwyczaj jest ona obliczana dla każdego okresu, w którym planowany jest przychód. Program oblicza okres ATP w dniach i oblicza bieżąca datę jako pierwszą datę dla ilości ATP. W pierwszym okresie ATP obejmuje dostępne zapasy ATP z potrąceniem zamówień odbiorców, które są należne lub zaległe.

ATP są obliczane za pomocą następującego wzoru:

ATP = ATP dla poprzedniego okresu + przyjęcia w bieżącym okresie - wydania w bieżącym okresie - wydana ilość netto dla każdego przyszłego okresu do momentu, gdy suma przyjęć dla wszystkich przyszłych okresów, łącznie z ostatnim okresem w zakresie, przekracza sumę wydań do przyszłego okresu włącznie.

Należy zauważyć, że obliczenie dostępności zapasów nie zawiera informacji w odróżnieniu od daty ważności i po upływie horyzontu czasowego dostępności zapasów, którego system oczekuje w przypadku, gdy ilość może zostać uzgodniona.

Jeśli nie ma już rozchodów lub przychodów do uwzględnienia, ilość ATP dla następujących dat jest taka sama jak ostatnia obliczona ilość ATP.

Jeśli wszystkie wymiary użyte dla towaru nie zostaną podane w momencie gdy następuje sprawdzenie ATP, nadal będzie można je określić dla rozchodów i przychodów. W takim przypadku w obliczeniu ATP przychody i rozchody muszą zostać zespolone do istniejących wymiarów, aby ograniczyć liczbę wierszy rozchodów i przychodów używanych w obliczaniu ATP.

Wyświetlana ilość ATP jest zawsze większa lub równa 0 (zero). Jeśli obliczenie da ujemną ilość ATP (na przykład, jeśli wcześniej zarezerwowana ilość przekracza dostępną ilość), ilość jest automatycznie ustawiona na 0.

### <a name="example"></a>Przykład

Pole **Horyzont czasowy wstecz dla popytu ATP** kontroluje, jak daleko wstecz na osi czasu mają być wyszukiwane opóźnione zamówienia popytowe lub rozchody towarów. Pole **Horyzont czasowy wstecz dla podaży ATP** kontroluje, jak daleko wstecz na osi czasu mają być wyszukiwane opóźnione zamówienia podażowe lub przyjęcia towarów. Na przykład, jeśli zamówienia, które są opóźnione tylko o siedem dni powinny być uwzględniane w obliczeniu ATP, oba pola powinny mieć wartość **7**.

Pola **Przesunięcie czasowe opóźnionego popytu ATP** i **Przesunięcie czasowe opóźnionej podaży ATP** kontrolują, kiedy opóźniony popyt lub podaż mają być uwzględniane w obliczeniach ATP. Na przykład, jeśli opóźnione popyt i podać mają być uwzględniany w obliczeniach ATP pojutrze, w obu polach powinna być wartość **2**. Wartość **2** oznacza, że ilość towaru na opóźnionym zamówieniu zakupu, która powinna być uwzględniona w obliczeniu ATP, będzie widoczna jako dostępna dwa dni po dacie bieżącej.

W następującym przykładzie pola **Horyzont czasowy wstecz dla popytu ATP** i **Horyzont czasowy wstecz dla podaży ATP** otrzymują wartość **7**, a pola **Przesunięcie czasowe opóźnionego popytu ATP** i **Przesunięcie czasowe opóźnionego popytu ATP** otrzymują wartość **1**.

Zamówienie zakupu na 200 sztuk produktu, które powinny zostać dostarczone trzy dni temu, jeszcze nie zostało zrealizowane. W związku z tym wiersz zamówienia sprzedaży na 75 sztuk tego samego produktu, który powinien był zostać wysłany wczoraj, nie został wysłany.

Klient dzwoni i chce zamówić 150 sztuk tego samego produktu. Gdy sprawdzasz dostępność produktu, okazuje się, że inne zamówienie zakupu na 100 sztuk tego produktu zostanie dostarczone 10 dni później.

Tworzysz wiersz zamówienia sprzedaży dla produktu i wprowadzasz ilość **150**.

Ponieważ metodą kontroli daty dostawy jest ATP, obliczana jest data ATP, aby ustalić najwcześniejszą możliwą datę wysyłki. Na podstawie ustawień opóźnione zamówienie zakupu i zamówienie sprzedaży są uwzględniane i otrzymana ilość ATP dla bieżącej daty wynosi 0. Następnego dnia, gdy towary z opóźnionego zamówienia zakupu mają zostać odebrane, ilość ATP jest obliczana jako większa niż 0 (w tym przypadku wynosi 125). Jednak 10 dni od teraz, kiedy oczekuje się przyjęcia towarów z dodatkowego zamówienia zakupu na 100 sztuk towaru, ilość ATP jest większa niż 150.

Z tego powodu data wysyłki jest ustawiana na 10 dni od teraz na podstawie obliczeń ATP. Teraz można powiedzieć odbiorcy, że żądana ilość towaru może zostać dostarczona 10 dni od teraz.

## <a name="ctp-calculations"></a>Obliczenia CTP

Funkcja CTP umożliwia odbiorcy realną datę, kiedy można obiecać określone towary. Dla każdego wiersza sprzedaży można podać datę z uwzględnieniem istniejących dostępnych zapasów, zdolności produkcyjnych oraz czasów transportu.

CTP rozszerza funkcje ATP, biorąc pod uwagę informacje o zdolnościach produkcyjnych. Podczas gdy w atp jest uwzględniana tylko dostępność materiałów i zakłada się nieskończone zasoby zdolności produkcyjnych, w usługach CTP jest uwzględniana dostępność zarówno materiałów, jak i zdolności produkcyjnych. Dzięki temu można uzyskać bardziej realny obraz tego, czy popyt może być zatrzymany w danym czasie.

CTP działa nieco inaczej, w zależności od używanego głównego aparatu planowania (Optymalizacja planowania lub wbudowany aparat). CTP dla optymalizacji planowania obecnie obsługuje tylko podzestaw scenariuszy CTP, które są obsługiwane przez wbudowany aparat.

Aby uzyskać szczegółowe informacje o tym, jak skonfigurować i używać CTP dla każdego silnika, zobacz [Oblicz daty dostawy zamówień sprzedaży za pomocą CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

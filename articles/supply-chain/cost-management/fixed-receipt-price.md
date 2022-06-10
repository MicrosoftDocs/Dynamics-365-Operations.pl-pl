---
title: Odchylenia od ceny ewidencyjnej
description: W tym temacie wyjaśniono, jak można skonfigurować i używać stałych cen odbiorów w programie Microsoft Dynamics 365 Supply Chain Management.
author: raprofit
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 8e26d84ddc309249d8bd6e54987ad3ae8eed68f0
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770304"
---
# <a name="fixed-receipt-price"></a>Odchylenia od ceny ewidencyjnej

[!include [banner](../includes/banner.md)]

**Stała cena przyjęcia** to opcja, którą możesz wybrać w grupie modelu artykułu, gdy używasz modelu inwentaryzacji innego niż *Koszt standardowy* lub *Średnia ważona krocząca*. We wczesnych wersjach Microsoft Dynamics AX opcja ta nosiła nazwę **Koszt standardowy**. Została ona przemianowana na **stałą cenę przyjęcia**, gdy w Dynamics AX 2012 wprowadzono nowy model inwentaryzacji kosztów standardowych. W tym temacie wyjaśniono, jak można skonfigurować i używać stałych cen odbiorów w programie Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>O stałych cenach odbiorów

Gdy zaznaczysz pole wyboru **Stała cena odbioru** na stronie **Grupa modelu jednostki** dla danej pozycji, system używa ceny odbioru jako kosztu standardowego dla odbioru. Jeśli cena zakupu i domyślna cena kosztu artykułu skonfigurowana dla danego produktu różnią się, różnica jest księgowana na koncie **Zysk ze stałej ceny przyjęcia** lub **Strata ze stałej ceny przyjęcia** i kompensowana na koncie **Kompensata ze stałej ceny przyjęcia**, które określasz na stronie **Profil księgowania zapasów**.

Ponieważ opcja **Stała cena otrzymania** jest używana w połączeniu z różnymi modelami inwentaryzacji (takimi jak pierwsze weszło, pierwsze wyszło (FIFO); ostatnie weszło, pierwsze wyszło (LIFO); oraz średnia ważona), proces *zamknięcia i korekty inwentaryzacji* nadal będzie tworzył rozliczenia i korekty zgodnie z zasadą inwentaryzacji, którą wybierzesz na stronie **Grupa modeli pozycji**. Jednak korekty są dokonywane tylko w odniesieniu do wydań z zapasów.

Na przykład skonfigurowałeś produkt z grupą modeli artykułów, w której pole **Model zapasów** jest ustawione na *FIFO* i wybrana jest opcja **Stała cena odbioru**. Kiedy otrzymujesz zapasy poprzez zamówienie zakupu, wartość zapasów jest ustawiana na wartość domyślnej ceny kosztu wytworzenia danej pozycji w momencie otrzymania produktu. Kiedy wystawiasz fakturę za zamówienie zakupu, jeśli cena na fakturze jest inna, system zapisuje na koncie inwentaryzacyjnym domyślną cenę nabycia wydanego produktu. Różnicę przenosi na rachunek zysków i strat z tytułu stałej ceny wpływów. Później, gdy sprzedajesz lub zużywasz produkt, system używa średniej bieżącej dla danej pozycji w momencie zaksięgowania faktury za zamówienie sprzedaży (chyba że używasz oznaczeń).

Kiedy uruchamiasz proces *Zamknięcie zapasów i korekta*, system tworzy rozliczenie z pierwszym wydaniem w stosunku do pierwszego przyjęcia. Różnica między ceną odbioru, która została użyta przy odbiorze, a średnią bieżącą, która została użyta na wydaniu, jest księgowana na nowym kuponie.

## <a name="enable-fixed-receipt-prices"></a>Włączanie stałych cen odbiorów

Aby włączyć stałe ceny odbioru dla artykułu, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy modeli pozycji**.
2. Utwórz nową grupę modeli przedmiotów lub wybierz istniejącą grupę modeli.
3. W zakładce **Metoda kalkulacji i ujmowania kosztów** zaznacz pole wyboru **Stała cena zakupu**.

    > [!NOTE]
    > Nie możesz zaznaczyć pola wyboru **Stała cena odbioru**, jeśli pole **Model zapasów** jest ustawione na *Koszt standardowy* lub *Średnia krocząca*.

4. Zamknij stronę.

Po włączeniu opcji **stałej ceny odbioru** musisz zaktualizować swój profil księgowania zapasów, wykonując poniższe kroki.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Księgowanie**.
1. W zakładce **Zamówienie** w kolumnie **Wybierz** zaznacz **Stały zysk z ceny odbioru**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. Ustaw nowy wiersz tak, aby dotyczył grupy modelu artykułu, dla której włączyłeś ustalanie cen w stałej cenie odbioru, i określ główne konto, które jest używane do rejestrowania zysków w stałej cenie odbioru dla zamówień zakupu. Skonfiguruj inne ustawienia według własnych potrzeb.
1. W kolumnie **Wybierz** wybierz **Stałą utratę ceny odbioru**. Dodaj nowy wiersz odnoszący się do grupy modelu artykułu, dla której włączyłeś ustalanie cen stałego odbioru, i określ główne konto, które jest używane do rejestrowania strat z tytułu ustalonych cen odbioru dla zamówień zakupu. Skonfiguruj inne ustawienia według własnych potrzeb.
1. W kolumnie **Wybierz** wybierz **Kompensacja stałej ceny odbioru**. Dodaj nowy wiersz odnoszący się do grupy modelu artykułu, dla której włączyłeś ustalanie cen stałych odbiorów, i określ główne konto, które jest używane do rejestrowania kompensat cen stałych odbiorów dla zamówień zakupu. Skonfiguruj inne ustawienia według własnych potrzeb.
1. W zakładce **Zapasy** w kolumnie **Wybierz** zaznacz **Stały zysk z ceny odbioru**. Dodaj nowy wiersz, który dotyczy grupy modeli artykułów, dla której włączyłeś ustalanie cen stałych wpływów, i określ główne konto, które jest używane do rejestrowania zysków ze stałych cen wpływów dla zapasów. Skonfiguruj inne ustawienia według własnych potrzeb.
1. W kolumnie **Wybierz** wybierz **Stałą utratę ceny odbioru**. Dodaj nowy wiersz, który dotyczy grupy modeli artykułów, dla której włączyłeś ustalanie cen stałych wpływów, i określ główne konto, które jest używane do rejestrowania zysków ze stałych cen strat zapasów. Skonfiguruj inne ustawienia według własnych potrzeb.

> [!NOTE]
> Zwykle zalecamy, by pola **Zysk po stałej cenie wpływu** i **Strata po stałej cenie wpływu** korzystały z tego samego konta głównego zarówno dla zamówień zakupu, jak i dla zapasów.

> [!IMPORTANT]
> Kiedy zmieniasz wartość w polu **Cena** w zakładce **Zarządzaj kosztami** na stronie **Wypuszczonych produktów**, system nie przeszacowuje automatycznie wartości zapasów, które są na stanie. Jako ręczne obejście tego problemu otwórz stronę **Zamykanie i dopasowywanie** i wybierz **Dopasowanie \> Dostępne** na pasku akcji. Następnie wybierz przedmioty, które są pod ręką, i dostosuj je do aktualnej ceny. Jedną z oczywistych zalet stosowania modelu inwentaryzacji opartego na koszcie standardowym jest to, że powoduje on automatyczne przeszacowanie wartości zapasów znajdujących się w magazynie.

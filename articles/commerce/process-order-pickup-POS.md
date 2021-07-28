---
title: Przetwarzaj pobrania zamówień odbiorcy w miejscu sprzedaży
description: W tym temacie wyjaśniono funkcje dostępne w aplikacji punkt sprzedaży (POS) do przetwarzania pobrania zamówień odbiorcy.
author: Hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 037c9fb8dfc7aca4535540d92aae3e0ce0f8c638
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352163"
---
# <a name="process-customer-order-pickups-in-pos"></a>Przetwarzaj pobrania zamówień odbiorcy w miejscu sprzedaży

[!include [banner](includes/banner.md)]

Podczas tworzenia [zamówienia odbiorcy](customer-orders-overview.md) na potrzeby pobrania w sklepie użytkownik sklepu może użyć punkt sprzedaży punktu sprzedaży w celu rozpoczęcia pobrania magazynu. W razie potrzeby program POS będzie uruchamiał ostateczne przechwycenie płatności. Spowoduje to także zakończenie księgowania zapasów i transakcji finansowych dla ilości pobrań.

Jeśli jesteś użytkownikiem sklepu, możesz wykonać odbiór, używając operacji **Odwołaj zamówienie** lub **Operacji realizacji zamówienia** w aplikacji punktu sprzedaży. Aby udostępnić operację **Pobrania**, należy wykonać jeden z poniższych kroków:

- Aby użyć operacji **Odwołaj zamówienie**, wyszukaj i wybierz zamówienie, które zostanie wybrane.
- Aby użyć operacji **Realizacji zamówienia**, wyszukaj i wybierz jeden lub więcej wierszy zamówienia.

Jeśli wybrane zamówienie lub wiersze zamówienia nie są skonfigurowane do odbioru w tym konkretnym sklepie lub jeśli zamówienie zostało już w pełni odebrane, operacja **Odbiór** będzie niedostępna.

![Operacja pobrania.](media/pickupoperation.png)

W wersjach rozwiązania Microsoft Dynamics 365 Commerce 10.0.17 i nowszych poprawiona funkcja **Ulepszone wrażenia użytkownika przy przetwarzaniu zamówień przy odbiorze w punkcie sprzedaży** obsługi zamówień w punkcie sprzedaży można włączona za pomocą programu Zarządzanie funkcjami w programie Commerce Headquarters. Jeśli ta funkcja jest wyłączona, użytkownicy nie mogą wybierać ilości do odbioru. Domyślnie pełna ilość zamówiona dla wiersza to ilość, która zostanie pobrana. To doświadczenie może być problematyczne, ponieważ użytkownicy mogą zapomnieć o wybraniu niektórych pozycji do odbioru, gdy dokonują odbioru w ramach realizacji zamówienia.

Poprawiona funkcja **Ulepszone wrażenia użytkownika przy przetwarzaniu zamówień przy odbiorze w punkcie sprzedaży** umożliwia użytkownikom większą kontrolę nad wyborem produktów, które będą odbierane oraz ilością tych produktów, które będą odbierane. Użytkownicy nie muszą wybierać każdego wiersza zamówienia sprzedaży na stronie realizacji zamówienia, zanim będą wybierać opcję **Odbierz**. Zostaną wyświetlone wszystkie towary, które można odebrać. Użytkownicy mogą określić wiele linii do odbioru, nawet jeśli wybrano tylko jedną linię produktów.

Po włączeniu funkcji **Popraw wygodę użytkownika w zakresie przetwarzania zamówień przy odbiorze w punkcie sprzedaży** i wybraniu operacji **Pobrania** zostanie wyświetlone okno dialogowe **Pobranie**. Tam możesz wybrać towary i ilości, które zostaną odebrane. Domyślnie każda zamówiona ilość, która ma zapasy w stanie pobranym lub zapakowanym, jest uznawana za kwalifikującą się do odbioru. Domyślnie ta ilość jest ustawiona jako ilość pobrania. Można zmienić wprowadzoną ilość, pod warunkiem, że nie jest to 0 (zero) i nie przekracza całkowitej otwartej (czyli niezafakturowanej) ilości dla wybranego wiersza.

![Okno dialogowe odbioru.](media/pickupselect.png)

Po wybraniu ilości, które mają zostać wybrane, a następnie wybraniu opcji **Odbierz**, zostanie wyświetlona strona transakcji. Jeśli funkcja [płatności za pomocą kanału handlu wielokanałowego](omni-channel-payments.md) jest włączona i w pliku znajdują się wstępnie autoryzowane płatności kartą kredytową, należy zastosować tę płatność.

Na stronie transakcji system oblicza należne kwoty, obliczając sumę należną za wybrane pozycje do odbioru, a następnie odejmując wszelkie wcześniej zastosowane depozyty lub autoryzowane płatności kartą kredytową. Musisz przetworzyć płatność, aby zakończyć transakcję pobrania. Jeśli [układ ekranu](pos-screen-layouts.md) strony transakcji jest tak skonfigurowany, że zawiera operację **Zakończ transakcję** i brak należnej kwoty, można ukończyć transakcję bez wybierania metody płatności. Jeśli operacja **Zakończ transakcję** jest niedostępny, możesz wybrać łącze **„należnq kwotq 0,00 PLN”** w okienku **Sumy**, aby zakończyć transakcję bez konieczności wybierania metody płatności.

![Strona transakcji pobrania zamówienia odbiorcy.](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Zmienianie wierszy lub ilości pobrania

Jeśli po wybraniu pozycji do pobrania musisz zmienić ilość pobrania, możesz wybrać opcję **Ustaw ilość**. Nie można ustawić ilości pobrania na **0** (zero) ani zwiększyć jej do wartości przekraczającej niezafakturowaną ilość, która pozostaje w zamówionym wierszu. Aby usunąć wiersz pobrania z koszyka transakcji, wybierz opcję **Unieważnij transakcję**. Bieżąca transakcja zostanie zatrzymana, a przepływ operacji **Pobrania** zostanie uruchomiony ponownie.

Jeśli funkcja **Popraw wygodę użytkownika w zakresie przetwarzania zamówień przy odbiorze w punkcie sprzedaży** jest włączona, organizacje mogą dodać przycisk operacji **Zmień wiersze pobrania** w układzie ekranu strony transakcji. Po utworzeniu koszyka transakcji pobrania w programie POS i wybraniu towarów można wybrać opcję **Zmień wiersze pobrania**, jeśli musisz zmienić przedmioty do odbioru, ale nie chcesz anulować całej transakcji. W wyświetlanym oknie dialogowym **Zmiana wierszy pobrania** można zmieniać elementy i ilości pobrania. Koszyk transakcji jest następnie aktualizowany, aby odzwierciedlić wprowadzone zmiany.

![Okno dialogowe zmiany elementów pobrania.](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
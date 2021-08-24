---
title: Pokazywanie powiadomień o zamówieniach w aplikacji POS
description: W tym temacie opisano, w jaki sposób włączyć powiadomienia o zamówieniach w aplikacji POS i strukturze powiadomień.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7166afdb43c7e835170c5768a0767f2943222b19c00c7d0aaf067263845651f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714145"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Pokazywanie powiadomień o zamówieniach w aplikacji POS

[!include [banner](includes/banner.md)]

Współpracownikom sklepu można przypisać różne zadania w swoim sklepie, takie jak realizacja zamówień, przyjmowanie zapasów lub inwentaryzacja. Klient punktu sprzedaży (POS) udostępnia pojedynczą aplikację, w której współpracownicy mogą być powiadamiani o tych zadaniach. Struktura powiadomień w aplikacji POS rozwiązuje ten problem, umożliwiając pracownikom skonfigurowanie powiadomień opartych na rolach. Zaczynając w Dynamics 365 Retail z aktualizacją aplikacji 5 te powiadomienia mogą być skonfigurowane tylko w dla operacji POS.

System może wyświetlać powiadomienia dotyczące operacji *realizacji zamówienia*, a począwszy od wersji Commerce 10.0.18 mogą być także wyświetlane powiadomienia dotyczące operacji *wycofania zamówienia*. Jednak ponieważ struktura została zaprojektowana jako rozszerzalna, programiści docelowo będą mogli [napisać programy obsługi powiadomień](dev-itpro/extend-pos-notification.md) dla każdej operacji oraz powodować wyświetlanie tych powiadomień w aplikacji POS.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Włącz powiadomienia o realizacji lub wycofaniu zamówień

Aby włączyć powiadomienia dotyczące realizacji zamówienia lub operacji wycofania zamówienia, wykonaj następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje**.
1. Wyszukaj operację **Realizacja zamówienia** lub operacji **Odwołaj zamówienie**, a następnie zaznacz pole wyboru **Włącz powiadomienia**, aby określić, że struktura powiadomień ma nasłuchiwać zdarzeń programu obsługi tej operacji. Jeśli program obsługi jest zaimplementowany, powiadomienia o tej operacji będą wyświetlane w aplikacji POS.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Pracownicy \> Wszyscy pracownicy**.
1. Wybierz kartę **Commerce**, wybierz wiersz pracownika, a następnie **uprawnienia POS**. Wybierz skróconą kartę **Powiadomienia**, aby ją rozwinąć, a następnie dodaj operacje, dla których włączono powiadomienia. W przypadku konfigurowania pojedynczego powiadomienia dla pracownika upewnij się, że wartość **Kolejność wyświetlania** jest ustawiona na **1**. W przypadku konfigurowania więcej niż jednej operacji należy ustawić wartości **Kolejności wyświetlania**, aby wskazać kolejność wyświetlania powiadomień. 

      Powiadomienia są wyświetlane tylko dla operacji dodawanych na skróconej karcie **Powiadomienia**. Operacje w tym miejscu można dodawać tylko wtedy, gdy na stronie operacji w aplikacji pos zaznaczono pole wyboru **Włącz powiadomienia** dla tych **Operacji POS**. Ponadto powiadomienia o operacji są wyświetlane pracownikom tylko wtedy, gdy operacja została dodana do uprawnień wobec aplikacji POD dla tych pracowników.

    > [!NOTE]
    > Powiadomienia można zastępować na poziomie użytkownika. Otwórz rekord pracownika, wybierz opcję **Uprawnienia punktu sprzedaży**, a następnie zmodyfikuj subskrypcję powiadomień dla użytkownika.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. W polu **Interwał powiadomień** określ żądaną częstotliwość pobierania powiadomień. W przypadku niektórych powiadomień aplikacja POS musi wykonywać wywołania w czasie rzeczywistym do aplikacji zaplecza. Te wywołania zużywają moc obliczeniową aplikacji zaplecza. W związku z tym podczas ustawiania interwału między powiadomieniami należy wziąć pod uwagę zarówno swoje potrzeby biznesowe, jak i wpływ obsługi wywołań w czasie rzeczywistym na aplikację zaplecza. Wartość **0** (zero) powoduje wyłączenie powiadomień.
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**. Wybierz harmonogram **1060** (**Personel**), aby zsynchronizować ustawienia subskrypcji powiadomień, a następnie kliknij przycisk **Uruchom teraz**. Następnie wybierz harmonogram **1070** (**Konfiguracja kanału**), aby zsynchronizować interwał uprawnień, i kliknij przycisk **Uruchom teraz**.

## <a name="view-notifications-in-the-pos"></a>Wyświetlanie powiadomień w aplikacji POS

Po wykonaniu powyższych kroków pracownicy będą widzieć powiadomienia w aplikacji POS. Aby wyświetlić powiadomienia, wybierz ikonę powiadomień w prawym górnym rogu aplikacji POS. Zostanie wyświetlony panel powiadomień i wyświetlone są powiadomienia dotyczące operacji skonfigurowanych dla pracownika. 

Dla operacji **realizacji zamówienia** w panelu powiadomień pojawią się następujące grupy:

- **Odbiór w sklepie** — Ta grupa pokazuje liczbę poszczególnych linii zamówienia, które są zaplanowane do odbioru z bieżącego sklepu. Możesz wybrać numer w grupie, aby otworzyć operację **Realizacja zamówienia** z filtrem, tak aby wyświetlała tylko aktywne wiersze zamówienia, które są skonfigurowane do odbioru z bieżącego sklepu.
- **Wysyłka ze sklepu** — w tej grupie jest przedstawiana liczba poszczególnych wierszy zamówienia, które zostały skonfigurowane do wysyłki z bieżącego sklepu użytkownika. Możesz wybrać numer w grupie, aby otworzyć operację **Realizacja zamówienia** z przefiltrowanym widokiem, który pokazuje tylko aktywne wiersze zamówienia, które są skonfigurowane do wysyłki z bieżącego sklepu.

Dla operacji **odwołanie zamówienia** w panelu powiadomień pojawią się następujące grupy:

- **Zamówienia do realizacji** — w tej grupie jest przedstawiana liczba zamówień skonfigurowanych dla realizacji pobrania lub realizacji wysyłki dla bieżącego sklepu użytkownika. Możesz wybrać liczbę na grupę, aby otworzyć operację **Odwołaj zamówienie** z przefiltrowany widok, który pokazuje tylko otwarte zamówienia, które muszą zostać spełnione przez bieżący sklep użytkownika w celu pobrania w sklepie lub wysłania z scenariuszy sklepu.
- **Zamówienia do odbioru** — Ta grupa pokazuje liczbę zamówień, które są zaplanowane do odbioru z bieżącego sklepu. Możesz wybrać liczbę na grupę, aby otworzyć operację **Odwołaj zamówienie** z przefiltrowany widok, który pokazuje tylko otwarte zamówienia, które muszą zostać zrealizowane, aby klient mógł je odebrać z bieżącego sklepu użytkownika.
- **Zamówienia do wysyłki** — w tej grupie jest przedstawiana liczba zamówień do wysłania z bieżącego sklepu użytkownika. Możesz wybrać liczbę na grupę, aby otworzyć operację **Odwołaj zamówienie** z przefiltrowany widok, który pokazuje tylko otwarte zamówienia, które muszą zostać zrealizowane w celu wysyłki z bieżącego sklepu użytkownika.

Zarówno w przypadku powiadomień o realizacji zamówienia, jak i powiadomieniach o wycofaniu zamówienia, gdy proces odbiera nowe zamówienia, ikona powiadomienia zmienia się, aby wskazać, że są nowe powiadomienia, a licznik dla odpowiednich grup jest aktualizowany. Grupy są odświeżane w regularnych odstępach czasu, ale użytkownicy aplikacji POS mogą również odświeżać je ręcznie w dowolnym momencie, naciskając **Odśwież** znajdujący się obok grupy. Ponadto jeśli w grupie znajdzie się nowa pozycja, której pracownik jeszcze nie oglądał, obok grupy pojawi się symbol serii.

## <a name="enable-live-content-on-pos-buttons"></a>Włączanie przekazywania zawartości na żywo na przyciskach aplikacji POS

Przyciski aplikacji POS mogą teraz pokazywać liczbę, aby ułatwić pracownikom identyfikowanie, które zadania wymagają ich natychmiastowej uwagi. Aby ta liczba była wyświetlana na przycisku aplikacji POS, należy dokonać konfiguracji powiadomień opisanej we wcześniejszej części tego tematu (tzn. trzeba włączyć powiadomienia dla operacji, ustawić interwał powiadamiania oraz zaktualizować grupę uprawnień pracownika wobec aplikacji POS). Ponadto należy otworzyć projektanta siatki przycisków, wyświetlić właściwości przycisku i zaznaczyć pole wyboru **Włącz zawartości na żywo**. W polu **Wyrównanie zawartości** można określić, gdzie liczba ma być wyświetlana: w prawym górnym rogu (**Do góry, do prawej**) czy na środku (**Środek**) przycisku.

> [!NOTE]
> Zawartości na żywo można włączyć dla operacji tylko wtedy, gdy na stronie **Operacje aplikacji POS** zaznaczono dla nich pole wyboru **Włącz powiadomienia**, jak opisano we wcześniejszej części tego tematu.

Poniższa ilustracja przedstawia ustawienia przekazywania zawartości na żywo w konstruktorze siatki przycisków.

![Ustawienia zawartości aktywnej w projektancie siatki przycisków.](./media/ButtonGridDesigner.png "Ustawienia zawartości aktywnej w projektancie siatki przycisków")

Aby wyświetlić na przycisku licznik powiadomień, należy upewnić się, że jest aktualizowany właściwy układ ekranu. Aby określić układ ekranu używany przez punkt sprzedaży, wybierz ikonę **Ustawienia** w prawym górnym rogu i zanotuj jej **Identyfikator układu ekranu** i **Rozdzielczość układu**. Za pomocą przeglądarki Edge przejdź do strony **Układ ekranu**, znajdź **Identyfikator układu ekranu** i **Rozdzielczość układu** określone powyżej i zaznacz pole wyboru **Włącz zawartość na żywo**. Przejdź do **Sprzedaż detaliczna i komercyjna \> IT sprzedaży \> Harmonogram dystrybucji** i uruchom zadanie 1090 (rejestry), aby zsynchronizować zmiany w układzie.

![Znajdowanie układu ekranu używanego w punkcie sprzedaży.](./media/Choose_screen_layout.png "Znajdź układy ekranu")

Na poniższej ilustracji przedstawiono efekt wybrania opcji **Do góry, do prawej** i **Środek** w polu **Wyrównanie zawartości** dla przycisków o różnej wielkości.

![Aktywna zawartość na przyciskach aplikacji POS.](./media/ButtonsWithLiveContent.png "Aktywna zawartość na przyciskach aplikacji POS")

[!INCLUDE[footer-include](../includes/footer-banner.md)]

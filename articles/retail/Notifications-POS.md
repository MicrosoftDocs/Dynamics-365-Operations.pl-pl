---
title: Pokazywanie powiadomień o zamówieniach w aplikacji POS
description: W tym temacie opisano, w jaki sposób włączyć powiadomienia o zamówieniach w aplikacji POS i strukturze powiadomień.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: e7aceed380f6722353574470d6dee75ebe105c18
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1530277"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Pokazywanie powiadomień o zamówieniach w aplikacji POS

[!include [banner](includes/banner.md)]

We współczesnym środowisku sprzedaży detalicznej do pracowników sklepu są przypisane różne zadania, takie jak pomoc klientom, wprowadzanie transakcji, przeprowadzanie inwentaryzacji i odbieranie zamówień w sklepie. Klient punktu sprzedaży (POS) do jedna zintegrowana aplikacja, w której pracownicy mogą wykonywać te i wiele innych zadań. Ponieważ w ciągu dnia trzeba wykonywać różne zadania, pracownicy mogą potrzebować powiadomień, jeżeli coś wymaga ich uwagi. Struktura powiadomień w aplikacji POS rozwiązuje ten problem, umożliwiając pracownikom skonfigurowanie powiadomień opartych na rolach. W Microsoft Dynamics 365 for Retail z aktualizacją aplikacji 5 te powiadomienia mogą być skonfigurowane tylko w dla operacji POS.

Obecnie system może być pokazywać powiadomienia tylko dla operacji realizacji zamówień. Jednak ponieważ struktura została zaprojektowana jako rozszerzalna, programiści docelowo będą mogli napisać programy obsługi powiadomień dla każdej operacji oraz powodować wyświetlanie tych powiadomień w aplikacji POS.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Włączanie powiadomień dla operacji realizacji zamówień

Aby włączyć powiadomienia dla operacji realizacji zamówień, wykonaj poniższe czynności.

1. Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Operacje**.
2. Wyszukaj operację **Realizacja zamówienia**, a następnie zaznacz pole wyboru **Włącz powiadomienia**, aby określić, że struktura powiadomień ma nasłuchiwać zdarzeń programu obsługi tej operacji. Jeśli program obsługi jest zaimplementowany, powiadomienia o tej operacji będą wyświetlane w aplikacji POS.
3. Wybierz kolejno opcje **Handel detaliczny** &gt; **Pracownicy etatowi** &gt; **Pracownicy**&gt; i na karcie Handel detaliczny otwórz uprawnienia wobec aplikacji POS związane z pracownikiem. Rozwiń skróconą kartę **Powiadomienia**, dodaj operację **Realizacja zamówienia**, a następnie w polu **Kolejność wyświetlania** ustaw wartość **1**. Jeżeli skonfigurowano więcej niż jedno powiadomienie, to pole służy do określenia ich kolejności. Powiadomienia o niższej wartości w polu **Kolejność wyświetlania** są wyświetlane nad powiadomieniami mającymi wyższą wartość. Powiadomienia, które w polu **Kolejność wyświetlania** mają wartość **1**, znajdują się na samej górze.

    Powiadomienia są wyświetlane tylko dla operacji dodanych na skróconej karcie **Powiadomienia**, a operacje można tam dodawać tylko wtedy, gdy zaznaczono dla nich pole wyboru **Włącz powiadomienia** na stronie **Operacje aplikacji POS**. Ponadto powiadomienia o operacji są wyświetlane pracownikom tylko wtedy, gdy operacja została dodana do uprawnień wobec aplikacji POD dla tych pracowników.

    > [!NOTE]
    > Powiadomienia można zastępować na poziomie użytkownika. Otwórz rekord pracownika, wybierz opcję **Uprawnienia punktu sprzedaży**, a następnie zmodyfikuj subskrypcję powiadomień dla użytkownika.

4. Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile funkcji**. W polu **Interwał powiadomień** określ żądaną częstotliwość pobierania powiadomień. W przypadku niektórych powiadomień aplikacja POS musi wykonywać wywołania w czasie rzeczywistym do aplikacji zaplecza. Te wywołania zużywają moc obliczeniową aplikacji zaplecza. W związku z tym podczas ustawiania interwału między powiadomieniami należy wziąć pod uwagę zarówno swoje potrzeby biznesowe, jak i wpływ obsługi wywołań w czasie rzeczywistym na aplikację zaplecza. Wartość **0** (zero) powoduje wyłączenie powiadomień.
5. Wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**. Wybierz harmonogram **1060** (**Personel**), aby zsynchronizować ustawienia subskrypcji powiadomień, a następnie kliknij przycisk **Uruchom teraz**. Następnie wybierz harmonogram **1070** (**Konfiguracja kanału**), aby zsynchronizować interwał uprawnień, i kliknij przycisk **Uruchom teraz**.

## <a name="view-notifications-in-the-pos"></a>Wyświetlanie powiadomień w aplikacji POS

Po wykonaniu powyższych kroków pracownicy będą widzieć powiadomienia w aplikacji POS. Aby wyświetlić powiadomienia, naciśnij ikonę powiadomień w prawym górnym rogu aplikacji POS. Zostanie wyświetlone centrum powiadomień z powiadomieniami o operacji realizacji zamówień. Centrum powiadomień powinno przedstawiać następujące grupy w operacji realizacji zamówień:

- **Odbiór w sklepie** — ta grupa pokazuje liczbę zamówień, których sposób dostawy to **Odbiór**, a odbiór jest zaplanowany z bieżącego sklepu. Naciśnięcie liczby na grupie spowoduje otwarcie strony **Realizacja zamówienia**. W tym przypadku strona będzie wyfiltrowana, tak aby pokazywała tylko aktywne zamówienia skonfigurowane do odbioru z bieżącego sklepu.
- **Wyślij z magazynu** — ta grupa pokazuje liczbę zamówień, których sposób dostawy to **Wysyłka**, a wysyłka jest zaplanowana z bieżącego sklepu. Naciśnięcie liczby na grupie spowoduje otwarcie strony **Realizacja zamówienia**. W tym przypadku strona będzie wyfiltrowana, tak aby pokazywała tylko aktywne zamówienia skonfigurowane do wysyłki z bieżącego sklepu.

Gdy do sklepu zostaną przypisane nowe zamówienia do realizacji, ikona powiadomień zmieni się, informując o nowych powiadomieniach, a liczby odpowiednich grup zostaną zaktualizowane. Grupy są odświeżane w regularnych odstępach czasu, ale użytkownicy aplikacji POS mogą również odświeżać je ręcznie w dowolnym momencie, naciskając przycisk **Odśwież** znajdujący się obok grupy. Ponadto jeśli w grupie znajdzie się nowa pozycja, której pracownik jeszcze nie oglądał, obok grupy pojawi się symbol serii.

## <a name="enable-live-content-on-pos-buttons"></a>Włączanie przekazywania zawartości na żywo na przyciskach aplikacji POS

Przyciski aplikacji POS mogą teraz pokazywać liczbę, aby ułatwić pracownikom identyfikowanie, które zadania wymagają ich natychmiastowej uwagi. Aby ta liczba była wyświetlana na przycisku aplikacji POS, należy dokonać konfiguracji powiadomień opisanej we wcześniejszej części tego tematu (tzn. trzeba włączyć powiadomienia dla operacji, ustawić interwał powiadamiania oraz zaktualizować grupę uprawnień pracownika wobec aplikacji POS). Ponadto należy otworzyć projektanta siatki przycisków, wyświetlić właściwości przycisku i zaznaczyć pole wyboru **Włącz zawartości na żywo**. W polu **Wyrównanie zawartości** można określić, gdzie liczba ma być wyświetlana: w prawym górnym rogu (**Do góry, do prawej**) czy na środku (**Środek**) przycisku.

> [!NOTE]
> Zawartości na żywo można włączyć dla operacji tylko wtedy, gdy na stronie **Operacje aplikacji POS** zaznaczono dla nich pole wyboru **Włącz powiadomienia**, jak opisano we wcześniejszej części tego tematu.

Poniższa ilustracja przedstawia ustawienia przekazywania zawartości na żywo w konstruktorze siatki przycisków.

![Ustawienia zawartości na żywo w konstruktorze siatki przycisków](./media/ButtonGridDesigner.png "Ustawienia zawartości na żywo w konstruktorze siatki przycisków")

Aby wyświetlić na przycisku licznik powiadomień, należy upewnić się, że jest aktualizowany właściwy układ ekranu. Aby określić układ ekranu używany przez punkt sprzedaży, wybierz ikonę **Ustawienia** w prawym górnym rogu i zanotuj jej **Identyfikator układu ekranu** i **Rozdzielczość układu**. Za pomocą przeglądarki krawędzi przejdź do strony **Układ ekranu** w Dynamics 365 for Finance and Operations, znajdź **Identyfikator układu ekranu** i **Rozdzielczość układu** określone powyżej i zaznacz pole wyboru **Włącz zawartość na żywo**. Przejdź do **Sprzedaż detaliczna > IT sprzedaży detalicznej > Harmonogram dystrybucji** i uruchom zadanie 1090 (rejestry), aby zsynchronizować zmiany w układzie. 

![Znajdowanie układu ekranu używanego w punkcie sprzedaży](./media/Choose_screen_layout.png "Znajdź układ ekranu ")

Na poniższej ilustracji przedstawiono efekt wybrania opcji **Do góry, do prawej** i **Środek** w polu **Wyrównanie zawartości** dla przycisków o różnej wielkości.

![Zawartość na żywo na przyciskach aplikacji POS](./media/ButtonsWithLiveContent.png "Zawartość na żywo na przyciskach aplikacji POS")

---
title: Włączanie wielu metod dostawy dla zamówień klientów
description: W tym artykule opisano funkcje rozwiązania Microsoft Dynamics 365 Commerce, które umożliwiają tworzenie zamówień odbiorcy do odebrania w sklepie.
author: hhainesms
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e4d8883b3dc1c4a0e12bcb00b6441f76d73da92e
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831592"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Włączanie wielu metod dostawy dla zamówień klientów

[!include [banner](includes/banner.md)]


W Microsoft Dynamics 365 Commerce mogą definiować wiele trybów dostawy, które klienci lub współpracownicy mogą wybrać podczas tworzenia zamówienia, które będzie odebrane w sklepie. W ten sposób organizacje mogą oferować klientom wiele opcji odbioru. Na przykład wielu sprzedawców oferuje klientom możliwość wyboru odbioru w sklepie lub odbioru „przy krawężniku”. System Commerce obsługuje konfigurację różnych trybów odbioru. Użytkownicy mogą korzystać z nich podczas tworzenia zamówień dla klientów w ramach dowolnego kanału handlowego (elektroniczny, call center, sklep).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Włączanie i konfiguracja wielu metod dostawy dla odbiorów

Funkcja **Obsługa wielu sposobów dostarczania przesyłek pobraniowych** w przestrzeni roboczej **Zarządzanie funkcjami** w Commerce headquarters stała się obowiązkowa i powinna być włączona w środowisku.

Jeśli wcześniej zdefiniowałeś tryb dostawy po odbiór na stronie **Parametry Commerce**, tryb ten pojawi się w bieżącej konfiguracji trybów dostawy po odbiór.

![Metody odbioru na stronie parametrów Commerce.](media/multiplepickupparameter.png)

Możesz zdefiniować wiele trybów dostawy przy odbiorze na siatce **Tryb dostawy przy odbiorze** w zakładce **Parametry handlu** > **Zamówienia klientów** > **Tryb dostawy**.  

Pola **Sposób realizacji dostawy — odbiór** i **Elektroniczny tryb dostawy** oraz opcja **Pokazuj tylko metody dostawy przewoźnika** zostały przeniesione na tą skróconą kartę.

Przed skonfigurowaniem trybów dostawy do odbioru należy zdefiniować metody dostawy. Na stronie **Metody dostawy** w module Commerce Headquarter, można dodawać metody dostawy, które powinny być traktowane jako metody odbioru. Upewnij się, że została ukończona cała konfiguracja. Na przykład, jeśli oferujesz odbiór „przy krawężniku” jako opcję dostawy dla kupujących online w niektórych sklepach, musisz utworzyć w tym celu nowy tryb dostawy. Możesz utworzyć ten tryb dostawy, używając „odbiór przy krawężniku” jako opisu. Następnie należy upewnić się, że tryb dostawy „przy krawężniku” jest zmapowany do wszystkich kanałów Commerce, które mogą go oferować, w tym sklepów internetowych, które mogą oferować tę opcję i poszczególnych kanałów sklepowych, które będą oferować tę metodę realizacji. Sposoby dostawy muszą być również powiązane z produktami. W tym przykładzie, jeśli istnieją pewne produkty, które nie mogą być zrealizowane za pomocą „odbioru przy krawężniku”, należy upewnić się, że te elementy są wykluczone. Po zakończeniu dodawania nowych trybów dostawy należy uruchomić zadanie **Metody dostawy procesów**, aby utworzyć relacje między trybem dostawy, kanałami i towarami. Po zakończeniu zadania otwórz stronę **Harmonogram dystrybucji** w module Commerce Headquarter, a następnie uruchom zadanie dystrybucji **1120**, aby upewnić się, że odpowiednie bazy danych kanałów Commerce są aktualizowane przy użyciu nowej konfiguracji trybu dostawy.

![Przykład konfiguracji metody dostawy dla odebrania „przy krawężniku”.](media/pickupmodes.png)

Po zdefiniowaniu dodatkowych trybów odbioru należy dodać je do siatki **Metody dostawy — odbiór** na stronie **parametrów Commerce**. Następnie należy uruchomić odpowiednie zadania dystrybucji, aby zaktualizować odpowiednie bazy danych kanałów Commerce z tą zmianą konfiguracji.

> [!NOTE]
> Poza istniejącym trybem dostawy, który jest kopiowany do siatki **Metody dostawy — odbiór** po włączeniu **Obsługi wielu metod dostawy** dla każdej dodatkowej konfiguracji metody odbioru, należy skonfigurować nowe metody dostawy. Po dodaniu metod dostawy do **Metody odbioru — odbiór**, Commerce sprawdza, czy są już używane aktywne otwarte wiersze sprzedaży. Jeśli zostaną znalezione otwarte wiersze sprzedaży, zostanie wyświetlony komunikat o błędzie. Metody dostawy nie są uznawane za metody dostawy — odbioru, dopóki wszystkie otwarte wiersze sprzedaży, w których są używane, nie zostały zamknięte (zafakturowane lub anulowane).


### <a name="e-commerce-site-configurations"></a>Konfiguracje witryny handlu elektronicznego

Jeśli jest włączona **Obsługa wielu trybów odbioru**, następujące moduły na stronach e-commerce wyświetlają nowe metody dostawy jako skonfigurowane:

- Pole zakupu
- Selektor sklepów
- Koszyk
- Informacje o pobraniu
- Potwierdzenie zamówienia
- Szczegóły zamówienia

Na stronach e-commerce nie są wymagane dodatkowe kroki w celu udostępnienia trybów dostawy — odbiór.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Praca z wieloma metodami dostawy dla odbiorów

Jeśli dla kanału jest dostępnych wiele trybów dostawy — odbioru, w momencie oferowania produktów, do odbioru, oferowana jest ulepszona obsługa klienta. 

- W przypadku kanałów e-commerce, kupujący może wybrać dowolny dostępny tryb dostawy — odbioru, który jest dostępny. Na przykład sprzedawca, który określa dwa tryby dostawy dostawy — odbioru (odbiór w sklepie i „przy krawężniku”), w tabeli **Metody dostawy — odbiór** skonfiguruje obydwa typy. Oba z nich są ważne dla kanału realizacji zamówienia oraz produktu, który jest obecnie kupowany. W takim przypadku klient może wybrać preferowany tryb dostawy — odbiór. Wybrany tryb dostawy jest następnie przekształcany w tryb dostawy, który jest połączony z wierszem zamówienia sprzedaży podczas tworzenia zamówienia w module Commerce Headquarter.

    ![Wybieranie opcji odbioru w e-commerce.](media/pickupecommerce.png)

- W kanałach sklepowych, jeśli zamówienie do odbioru jest tworzone za pośrednictwem aplikacji punktu sprzedaży (POS), pracownik otrzymuje monit o wybranie jednego z dostępnych trybów dostawy (o ile zostały skonfigurowane). Jeśli dla danego kanału i towaru dostępny jest tylko jeden prawidłowy tryb dostawy — odbiór, pracownikowi nie zostanie wyświetlony monit. W takim przypadku w wierszach zamówienia jest automatycznie stosowany dostępny tryb dostawy — odbiór.

    ![Wybieranie opcji odbioru w aplikacji punktu sprzedaży.](media/pickuppos.png)

- W przypadku kanałów biura obsługi, gdy użytkownicy tworzą zlecenia odbioru, mogą ręcznie wybrać dowolny zdefiniowany tryb dostawy, który jest połączony z kanałem biura obsługi. Następnie system sprawdza, czy wybrany tryb dostawy odbioru może być używany podczas zamawiania towaru połączonego. Jeśli w kanale biura obsługi jest wybrany tryb dostawy pobrania, wiersze zamówienia sprzedaży muszą być połączone z prawidłowym magazynem sklepu. Jeśli w wierszu sprzedaży biura obsługi jest zdefiniowany magazyn niesklepowy, w tym wierszu sprzedaży nie można określić trybu dostawy — odbioru.
- Współpracowników może skorzystać z operacji **Odwoływania zamówień** lub **Realizacji zamówień** w aplikacji punktu sprzedaży w celu pobrania listy zamówień lub wierszy zamówień do odbioru. Jeśli w ramach sprzedaży zostanie użyty wstępnie zdefiniowany filtr wyszukiwania w celu wyświetlenia wszystkich zamówień, które zostaną odebrane w bieżącym sklepie, zostaną zmodyfikowane kwerendy, aby upewnić się, że wyniki wyszukiwania uwzględniają wszystkie kwalifikujące się zamówienia, w których jest używany dowolny tryb dostawy/odbioru. Użytkownicy aplikacji punktu sprzedaży mogą również stosować istniejące filtry w celu zawężenia listy zamówień do określonego trybu dostawy odbioru. Na przykład mogą być wyświetlane tylko zamówienia do odbioru „przy krawężniku”.

    ![Filtr dla trybów dostawy do odbioru zastosowany do listy zamówień wycofania.](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Informacje ważne dla funkcji zarządzania zamówieniami rozdzielonymi

[Funkcje zarządzania zamówieniami rozproszonymi (DOM)](./dom.md) w module Commerce ignorują wszystkie wiersze sprzedaży oznaczone do odbioru w sklepie. Te funkcje zostały zaktualizowane, aby upewnić się, że wiersze sprzedaży połączone z skonfigurowanymi metodami dostawy odbioru pomijają logikę modelu DOM i nie zostaną ponownie przydzielone do nowego magazynu realizacji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

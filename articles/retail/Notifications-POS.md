---
title: "Wyświetlanie powiadomień o zamówieniu w punkcie sprzedaży"
description: "W tym temacie opisano, w jaki sposób włączyć powiadomienia o zamówieniu w punkcie sprzedaży oraz strukturę powiadomień, którą można rozszerzyć na inne operacje."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: aea36591a81f727059e37a958efa62a9ebde9d9d
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2017

---

# <a name="display-notifications-in-point-of-sale"></a>Wyświetlanie powiadomień w punkcie sprzedaży

We współczesnym środowisku sprzedaży detalicznej do pracowników sklepu są przypisane różne zadania, takie jak pomoc klientom, wprowadzanie transakcji, przeprowadzanie inwentaryzacji i odbieranie zamówień w sklepie. Klient Punkt sprzedaży (POS) umożliwia pracownikom wykonywanie tych i innych zadań w jednej aplikacji. Mając do wykonania różne zadania w ciągu dnia, pracownicy mogą potrzebować powiadomień, jeżeli coś wymaga ich uwagi. Struktura powiadomień w punkcie sprzedaży rozwiązuje ten problem, umożliwiając pracownikom skonfigurowanie powiadomień opartych na rolach. W rozwiązaniu Dynamics 365 for Retail z aktualizacją aplikacji 5 te powiadomienia można skonfigurować tylko dla operacji punktu sprzedaży.

Obecnie system umożliwia wyświetlenie powiadomień dla operacji realizacji zamówienia, jednakże strukturę opracowano pod kątem możliwości rozszerzenia, aby w przyszłości programiści mogli opracować program obsługi powiadomień dla dowolnej operacji i umożliwić wyświetlanie powiadomień w punkcie sprzedaży.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Włączanie powiadomień dla operacji realizacji zamówień

Aby włączyć powiadomienia dla operacji realizacji zamówień, należy wykonać opisane poniżej czynności:

 - Przejdź do strony **Operacje** (**Sprzedaż detaliczna** > **Ustawienia kanału** > **Ustawienia punktu sprzedaży** > **Punkt sprzedaży** > **Operacje**).
 - Wyszukaj operację Realizacja zamówienia i zaznacz pole wyboru **Włącz powiadomienia** dla tej operacji. Powoduje to, że struktura powiadomień nasłuchuje programu obsługi operacji realizacji zamówienia. Jeżeli program obsługi jest wdrożony, powiadomienia będą wyświetlane w punkcie sprzedaży, w przeciwnym wypadku powiadomienia nie będą wyświetlane dla tej operacji.
- Przejdź do uprawnień punktu sprzedaży POS związanych z pracownikami i na skróconej karcie **Powiadomienia** dodaj operację Realizacja zamówienia, ustawiając parametr „Kolejność wyświetlania” na 1. Jeżeli skonfigurowano więcej niż jedno powiadomienie, kolejność wyświetlania służy do rozmieszczenia powiadomień od góry do dołu, gdzie 1 znajduje się na górze. Można dodać tylko te operacje, dla których zaznaczono pole wyboru **Włącz powiadomienia**. Ponadto powiadomienia będą wyświetlane tylko dla operacji, które zostały dodane tutaj i tylko dla pracowników, dla których operacje zostały dodane do odpowiednich uprawnień punktu sprzedaży. 

> [!NOTE]
> Powiadomienia można pominąć na poziomie użytkownika, przechodząc do rekordu pracownika, wybierając opcję **Uprawnienia punktu sprzedaży**, a następnie edytując subskrypcję powiadomień użytkownika.

 - Przejdź do strony **Profil funkcji** (**Sprzedaż detaliczna** > **Ustawienia kanału** > **Ustawienia punktu sprzedaży** > **Profile punktów sprzedaży** > **Profile funkcji**). Zaktualizuj właściwość **Interwał powiadomień**, aby ustawić w minutach interwał pobierania powiadomień. Zalecamy ustawienie tej wartości na 10 minut, aby uniknąć niepotrzebnej komunikacji z centralą. Ustawienie interwału powiadomień na „0” spowoduje ich wyłączenie.  

 - Wybierz kolejno opcje **Handel detaliczny** > **Składniki IT w handlu detalicznym** > **Harmonogram dystrybucji**. Wybierz harmonogram „1060-Personel”, aby zsynchronizować ustawienia subskrypcji powiadomień, a następnie kliknij przycisk **Uruchom teraz**. Następnie zsynchronizuje interwał uprawnień, wybierając opcję „1070-Konfiguracja kanału”, a następnie kliknij przycisk **Uruchom teraz**. 

## <a name="view-notifications-in-pos"></a>Wyświetlanie powiadomień w punkcie sprzedaży

Po wykonaniu powyższych czynności pracownicy, dla których skonfigurowano powiadomienia, mogą wyświetlać je w punkcie sprzedaży. Aby wyświetlić powiadomienia, kliknij ikonę powiadomień na pasku tytułu punktu sprzedaży. Spowoduje to wyświetlenie centrum powiadomień zawierającego powiadomienia dla operacji realizacji zamówień. Centrum powiadomień powinno wyświetlić następujące grupy w operacji realizacji zamówień: 

- **Zamówienia oczekujące** — ta grupa zawiera liczbę zamówień, które są w stanie oczekiwania, na przykład wymagające zaakceptowania przez pracownika punktu sprzedaży, który ma wymagane uprawnienia do realizacji w sklepie. Kliknięcie numeru grupy spowoduje otwarcie strony **Realizacja zamówienia** odfiltrowanej w celu wyświetlenia tylko zamówień oczekujących przypisanych do sklepu w celu realizacji. Jeżeli zamówienia są automatycznie akceptowane przez sklep, liczba w tej grupie będzie wynosić zero.

- **Odbiór w sklepie** — ta grupa zawiera liczbę zamówień, których sposób dostawy to **Odbiór**, a odbiór jest zaplanowany z bieżącego sklepu. Kliknięcie numeru grupy spowoduje otwarcie strony **Realizacja zamówienia** odfiltrowanej w celu wyświetlenia tylko aktywnych zamówień ustawionych do odbioru w bieżącym sklepie.

- **Wyślij z magazynu** — ta grupa zawiera liczbę zamówień, których sposób dostawy to **Wysyłka**, a wysyłka jest zaplanowana z bieżącego sklepu. Kliknięcie numeru grupy spowoduje otwarcie strony **Realizacja zamówienia** odfiltrowanej w celu wyświetlenia tylko aktywnych zamówień ustawionych do wysyłki z bieżącego sklepu.

Po przypisaniu do sklepu nowych zamówień do realizacji ikona powiadomień zmieni się, informując o nowych powiadomieniach, a liczba odpowiednich grup zostanie zaktualizowana. Użytkownik może także kliknąć ikonę odświeżania obok nazwy operacji, aby natychmiast zaktualizować liczbę grup. Liczba zostanie także zaktualizowana z zastosowaniem wstępnie zdefiniowanego interwału. Każda grupa zawierająca nowy element niewidziany przez bieżącego pracownika będzie zawierać ikonę wybuchu informującą, że grupa zawiera nowy element. Kliknięcie kafelków w powiadomieniach spowoduje otwarcie określonej operacji, dla której skonfigurowano to powiadomienie. W powyższych scenariuszach kliknięcie powiadomień spowoduje otwarcie strony **Realizacja zamówienia** i przekazanie odpowiednich parametrów: zamówienia oczekujące, odbiór w sklepie i wysyłka ze sklepu. 

> [!NOTE]
> Powiadomienia o zamówieniach oczekujących zostaną włączone w najbliższej aktualizacji programu Dynamics 365 for Retail. 



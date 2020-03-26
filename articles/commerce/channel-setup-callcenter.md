---
title: Konfigurowanie kanału biura obsługi
description: W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 14cee020cc8aead627180343c82bf23534ae83c4
ms.sourcegitcommit: 0681a00d60c9f8cc8f7b9888b8c5ddf07279fc04
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3131738"
---
# <a name="set-up-a-call-center-channel"></a>Konfigurowanie kanału biura obsługi


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie


W Dynamics 365 Commerce biuro obsługi jest typem kanału sprzedaży detalicznej, który można zdefiniować w aplikacji. Zdefiniowanie kanału dla jednostek biura obsługi telefonicznej umożliwia systemowi na odtworzenie konkretnych danych i zamówień, które są domyślne dla zamówień sprzedaży. Firma może definiować wiele kanałów biura obsługi w module Commerce, dlatego należy zauważyć, że pojedynczy użytkownik może być połączony tylko z jednym kanałem biura obsługi. 

Przed utworzeniem nowego kanału biura obsługi, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Utwórz i skonfiguruj nowy kanał biura obsługi

Aby utworzyć i skonfigurować nowy kanał biura obsługi, wykonaj następujące kroki.

1. W panelu nawigacyjnym wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Biura obsługi \> Wszystkie biura obsługi**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę nowego kanału.
1. Wybierz odpowiednią **Firmę** z rozwijanego menu.
1. Wybierz odpowiednią lokalizację **Magazynu** z rozwijanego menu. Ta lokalizacja będzie używana jako domyślna wartość w zamówieniach sprzedaży utworzonych dla tego kanału biura obsługi połączenia, o ile nie zdefiniowano innych wartości domyślnych na poziomie odbiorcy lub towaru.
1. W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę. Te dane służą do automatycznego wypełniania domyślnych ustawień tworzenia rekordów odbiorców. Podczas tworzenia zamówień biura obsługi nie zaleca się tworzenia zamówień dla domyślnego odbiorcy.
1. W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail. Podczas tworzenia i przetwarzania zamówień rozmów telefonicznych profil powiadomień e-mail jest używany do wyzwalania automatycznych alertów e-mail dla odbiorców z informacjami o stanie zamówienia.
1. Podaj kod informacji o **Ręczna zmiana ceny**. Konieczne może być utworzenie najpierw kodu informacyjnego. Ten kod informacji określa zestaw kodów przyczyn, które użytkownik będzie monitowany o wybranie w przypadku korzystania z funkcji zastępowanie cen w zamówieniu biura obsługi.
1. Podaj kod informacji o **Kod wstrzymania**. Konieczne może być utworzenie najpierw kodu informacyjnego. Ten kod informacji określa zestaw opcjonalnych kodów przyczyn, które użytkownik będzie monitowany o wybranie w przypadku składania wstrzymanego zamówienia.
1. Podaj kod informacji o **Kredycie**. Konieczne może być utworzenie najpierw kodu informacyjnego. Kod ten udostępnia zestaw kodów przyczyn, z których użytkownik może wybierać, korzystając z funkcji kredytu zamówienia w serwisie telefonicznej w celu uzyskania dodatkowych zwrotów dla odbiorcy w związku z przyczynami obsługi klienta.
1. Opcjonalnie: konfiguruj wymiary finansowe na skróconej karcie **Wymiary finansowe**. Wprowadzone tutaj wymiary są domyślne w każdym zamówieniu sprzedaży utworzonym w tym kanale biura obsługi.
1. Kliknij przycisk **Zapisz**.

Poniższy rysunek przedstawia utworzenie nowego kanału biura obsługi.

![Nowy kanał biura obsługi](media/channel-setup-callcenter-1.png)

Poniższy obraz przedstawia przykład kanału biura obsługi.

![Przykład kanału biura obsługi](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Konfiguracja kanałów dodatkowych

Dodatkowe zadania wymagane dla konfiguracji kanału dla biura obsługi, obejmują Konfigurowanie metod płatności i metod dostawy.

Poniższy obraz pokazuje **Metody dostawy** i **Metody płatności** ustaw opcje na karcie **Konfiguracja**.

![Dodatkowe akcje konfiguracji kanału biura obsługi](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale. Użytkownicy będą zobowiązani do wybrania wstępnie zdefiniowanych metod płatności w celu połączenia ich z kanałem biura obsługi. Przed skonfigurowaniem metod płatności biura obsługi, należy najpierw skonfigurować główne metody płatności w **Retail i Commerce \> Konfiguracja kanału \> Metody płatności \> Metody płatności**.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku nawigacji wybierz metodę płatności z dostępnych wstępnie zdefiniowanych płatności.
1. Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności. W przypadku kart kredytowych, kart upominkowych lub kart lojalnościowych dodatkowe ustawienia są wymagane po wybraniu funkcji **ustawienia karty**. 
1. Skonfiguruj poprawne konta księgowania dla typu płatności w sekcji **księgowanie**.
1. W okienku akcji kliknij pozycję **Zapisz**.

Poniższy obraz przedstawia przykład kart i metod płatności gotówką.

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Ustaw metody dostawy

Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.  

Aby zmienić lub dodać metodę dostawy skojarzoną z kanałem biura obsługi, wykonaj następujące kroki.

1. W formularzu metody dostawy biura obsługi, wybierz opcję **Zarządzaj metodami dostawy**
1. W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.
1. W sekcji **Kanały sprzedaży** kliknij opcję **Dodaj wiersz**, aby dodać kanał biura obsługi. Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.
1. Upewnij się, że metoda dostawy została skonfigurowana z danymi na skróconej karcie **produkty** i **adresy**. Jeśli żadne produkty lub adresy dostawy nie są prawidłowe dla metody dostawy, wybranie ich podczas wprowadzania zamówienia spowoduje błędy.
1. Po dokonaniu jakichkolwiek zmian w metodach konfiguracji dostawy w ramach procesu obsługi zleceń należy uruchomić zadanie **Metody dostawy dla procesu**, aby rozłożyć matrycę zmiany. To zadanie można znaleźć, przechodząc **Retail i Commerce \> Retail i Commerce — składniki IT \> Metody dostawy dla procesu**.

Poniższy obraz przedstawia przykład kart i metodę dostawy.

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Konfigurowanie użytkowników kanału

Aby utworzyć zamówienie sprzedaży połączone z pracownikiem biura obsługi w module Commerce Headquarters, użytkownik tworzący zamówienie musi być połączony z kanałem biura obsługi. Użytkownik nie może ręcznie połączyć zamówienia sprzedaży utworzonego w module Commerce Headquarters z kanałem biura obsługi. Łącze jest systematyczne i jest oparte na użytkowniku i relacji użytkownika z kanałem biura obsługi. Użytkownik może być połączony tylko z jednym kanałem biura obsługi.

1. W okienku akcji wybierz kartę **Kanał** i wybierz opcję **Użytkownicy kanału**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wybierz istniejący **identyfikator użytkownika** z listy rozwijanej zaznacz, aby połączyć tego użytkownika z kanałem biura obsługi

Po zakończeniu konfiguracji użytkownika kanału i gdy użytkownik utworzy nowe zamówienie sprzedaży w module Commerce Headquarters, użytkownik tworzący zamówienie zostanie połączony ze swoim kanałem biura obsługi. Wszelkie konfiguracje dla tego kanału będą stosowane systematycznie w zamówieniu sprzedaży. Użytkownik może potwierdzić, który kanał biura obsługi jest połączony z danym zamówieniem sprzedaży, wyświetlając odwołanie do nazwy kanału w nagłówku zamówienia sprzedaży.


### <a name="set-up-price-groups"></a>Konfigurowanie grup cenowych

Grupy cenowe są opcjonalne, ale jeśli są używane, mogą określać, które ceny sprzedaży będą oferowane odbiorcom do realizacji zamówień w kanale biura obsługi. Jeśli grupa cenowa nie została skonfigurowana dla odbiorcy lub nie są stosowane grupy cenowe w katalogu w zamówieniu sprzedaży (przy użyciu pola **Identyfikator kodu źródłowego** w nagłówku zlecenia biura obsługi), Grupa cenowa w kanale jest używana do lokalizowania cen towarów. Jeśli w kanale biura obsługi nie znaleziono grupy cenowej, używane są domyślne ceny główne towaru. 

Aby skonfigurować grupę cenową, należy wykonać następujące czynności.

1. W okienku akcji kliknij kartę **Kanał** i wybierz opcję **Grupy cenowe**.
1. W okienku akcji kliknij **Nowy**.
1. Wybierz **grupę cenową sieci sprzedaży** z listy rozwijanej wyboru.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wymagania wstępne dotyczące konfiguracji kanału](channels-prerequisites.md)

[Funkcje sprzedaży przez biuro obsługi](call-center-functionality.md)

[Konfigurowanie opcji przetwarzania zamówień biura obsługi](set-up-order-processing-options.md)

[Katalogi biura obsługi](call-center-catalogs.md)

[Konfigurowanie i używanie alertów o oszustwie](set-up-fraud-alerts.md)

[Konfigurowanie programów sprzedaży ciągłej dla biur obsługi](set-up-continuity-program.md)

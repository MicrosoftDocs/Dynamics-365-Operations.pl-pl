---
title: Konfigurowanie kanału biura obsługi
description: W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002457"
---
# <a name="set-up-a-call-center-channel"></a>Konfigurowanie kanału biura obsługi


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

W Dynamics 365 Commerce biuro obsługi jest typem kanału sprzedaży detalicznej, który można zdefiniować w aplikacji. Zdefiniowanie kanału dla jednostek biura obsługi telefonicznej umożliwia systemowi na odtworzenie konkretnych danych i zamówień, które są domyślne dla zamówień sprzedaży. Firma można zdefiniować wiele kanałów biura obsługi w Commerce. 

Przed utworzeniem nowego kanału biura obsługi, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Utwórz i skonfiguruj nowy kanał biura obsługi

Aby utworzyć i skonfigurować nowy kanał biura obsługi, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Biura obsługi \> Wszystkie biura obsługi**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę nowego kanału.
1. Wybierz odpowiednią **Firmę** z rozwijanego menu.
1. Wybierz odpowiednią lokalizację **Magazynu** z rozwijanego menu.
1. W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.
1. W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.
1. Podaj kod informacji o **Ręczna zmiana ceny**. Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.
1. Podaj kod informacji o **Kod wstrzymania**. Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.
1. Podaj kod informacji o **Kredycie**. Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.
1. Wybierz opcję **Zapisz**.

Poniższy rysunek przedstawia utworzenie nowego kanału biura obsługi.

![Nowy kanał biura obsługi](media/channel-setup-callcenter-1.png)

Poniższy obraz przedstawia przykład kanału biura obsługi.

![Przykład kanału biura obsługi](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Konfiguracja kanałów dodatkowych

Dodatkowe zadania wymagane dla konfiguracji kanału dla biura obsługi, obejmują Konfigurowanie metod płatności i metod dostawy.

Poniższy obraz pokazuje **Metody dostawy** i **Metody płatności** ustaw opcje na karcie **Konfiguracja**.

![Dodatkowe akcje konfiguracji kanału biura obsługi](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku nawigacji wybierz żądaną metodę płatności.
1. W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.
1. Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład kart i metod płatności gotówką.

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Ustaw metody dostawy

Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.  

Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.
1. W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.
1. W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał. Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.

Poniższy obraz przedstawia przykład kart i metodę dostawy.

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Funkcje sprzedaży przez biuro obsługi](call-center-functionality.md)

[Konfigurowanie opcji przetwarzania zamówień biura obsługi](set-up-order-processing-options.md)

[Katalogi biura obsługi](call-center-catalogs.md)

[Konfigurowanie i używanie alertów o oszustwie](set-up-fraud-alerts.md)

[Konfigurowanie programów sprzedaży ciągłej dla biur obsługi](set-up-continuity-program.md)

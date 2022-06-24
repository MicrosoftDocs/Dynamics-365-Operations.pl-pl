---
title: Konfigurowanie kanału online
description: W tym artykule opisano, jak dodać utworzyć nowy kanał online w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fe137fe0c69a5b9613086c66366b064194b9b6c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864936"
---
# <a name="set-up-an-online-channel"></a>Konfigurowanie kanału online

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać utworzyć nowy kanał online w Microsoft Dynamics 365 Commerce.

Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej. Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi). Sklepy internetowe dają klientom możliwość zakupu produktów w sklepie internetowym detalisty oprócz sklepów detalicznych.

Aby utworzyć sklep internetowy w systemie commerce, należy najpierw utworzyć kanał online. Przed utworzeniem nowego kanału online, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).

Aby można było utworzyć nową witrynę, w Commerce musi być utworzony co najmniej jeden sklep internetowy. Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Utwórz i skonfiguruj nowy kanał online

Aby utworzyć i skonfigurować nowy kanał online, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy online**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę nowego kanału.
1. Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.
1. Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.
1. W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.
1. W polu **Waluta** wybierz odpowiednią walutę.
1. W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.
1. W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.
1. W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.
1. W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy rysunek przedstawia utworzenie nowego kanału online.

![Nowy kanał online.](media/channel-setup-online-1.png)

Poniższy obraz przedstawia przykład kanału online.

![Przykład kanału online.](media/channel-setup-online-2.png)

## <a name="assign-the-channel-to-a-commerce-scale-unit"></a>Przypisywanie kanału do Commerce Scale Unit

Twój nowy kanał musi być przypisany do Commerce Scale Unit. Aby uzyskać instrukcje, zobacz temat [Konfigurowanie kanałów do używania Commerce Scale Unit](../fin-ops-core/dev-itpro/deployment/initialize-retail-channels.md#configure-channels-to-use-commerce-scale-unit).

## <a name="set-up-languages"></a>Konfiguracja języków

Jeśli dana witryna handlu elektronicznego będzie obsługiwać wiele języków, rozwiń sekcję **Języki** i dodaj dodatkowe języki w razie potrzeby.

## <a name="set-up-payment-account"></a>Konfiguracja konta płatności

W sekcji **Konto płatności** można dodać innego dostawcę płatności. Aby uzyskać informacje o ustawieniu łącznika płatności Adyen, zajrzyj do [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Konfiguracja kanałów dodatkowych

Dodatkowe zadania wymagane dla konfiguracji kanału online, obejmują Konfigurowanie metod płatności, metod dostawy i przypisania grupy realizacji.

Poniższy obraz pokazuje opcje ustawień **Metody dostawy**, **Metody płatności** i **Przypisania grupy realizacji** na karcie **Konfiguracja**.

![Dodatkowe akcje konfiguracji kanału online.](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku nawigacji wybierz żądaną metodę płatności.
1. W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.
1. Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład kart i metod płatności gotówką.

![Przykład metod płatności.](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Ustaw metody dostawy

Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.  

Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.
1. W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.
1. W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał. Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.

Poniższy obraz przedstawia przykład kart i metodę dostawy.

![Ustaw metody dostawy.](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Konfiguracja przypisania grupy realizacji

Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.
1. Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.

![Konfiguracja przypisania grupy realizacji.](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne dotyczące konfiguracji kanału](channels-prerequisites.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)

[Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

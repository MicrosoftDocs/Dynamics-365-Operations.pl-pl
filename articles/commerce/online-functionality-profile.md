---
title: Tworzenie profilu funkcji online
description: W tym temacie opisano sposób tworzenia profilu funkcji online w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: d6dcbb5b9ea01035396e90a6809cb1568c3a4fc86def41cf36732588b5046da7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716201"
---
# <a name="create-an-online-functionality-profile"></a>Tworzenie profilu funkcji online

[!include [banner](includes/banner.md)]

W tym temacie przedstawiono omówienie konfigurowania profilu funkcji online dla rozwiązania Microsoft Dynamics 365 Commerce.

Profil funkcji online umożliwia używanie różnych ustawień dla kanałów online. Każdy kanał online musi określać profil funkcji online.

## <a name="create-an-online-functionality-profile"></a>Tworzenie profilu funkcji online

Poniższa procedura wyjaśnia, jak utworzyć profil funkcji online z poziomu aplikacji Centrali Commerce.

1. W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Profil** wprowadź identyfikator profilu.
1. W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).
1. W sekcji **funkcje** zmodyfikuj odpowiednio **koszyk**, **odbiorcy detaliczni** lub ustawienia **realizacji transakcji**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykładowy profil funkcji online.
  
![Przekład profilu funkcji online.](media/online-functionality-profile.png)

## <a name="functions"></a>Funkcje

- **Zagregowane produkty**: po włączeniu tej funkcji zezwala się koszykowi na aktualizację ilości w przypadku, gdy ten sam towar jest dodawany wielokrotnie.
- **Zezwalaj na realizację transakcji bez płatności**: Jeśli to pole jest włączone, ta funkcja obsługuje scenariusz, gdy towary dodawane do koszyka mają cenę 0,00 USD.
- **Utwórz odbiorcę w trybie asynchronicznym**: jest to ustawienie starsze w odniesieniu do kanałów handlu elektronicznego innych firm i nie dotyczy witryny Dynamics 365 e-Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Konfigurowanie kanału internetowego](channel-setup-online.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

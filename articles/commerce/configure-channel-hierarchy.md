---
title: Skonfiguruj kanał, aby używał hierarchii nawigacji kanału
description: W tym artykule opisano sposób konfigurowania kanału do użycia hierarchii nawigacji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: b15e6eee86880f0315f42b34056385f718cc6bf1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280401"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Skonfiguruj kanał, aby używał hierarchii nawigacji kanału


[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania kanału do użycia hierarchii nawigacji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Hierarchie nawigacji kanału organizują produkty w kategoriach, dzięki czemu produkty mogą być przeglądane w witrynie handlu elektronicznego lub w punktach sprzedaży (POS). Kanały sieci sprzedaży i online muszą być skonfigurowane za pomocą hierarchii nawigacji kanału.

## <a name="configure-the-channel"></a>Konfigurowanie kanału

Aby skonfigurować kanał do korzystania z hierarchii nawigacji kanału, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Konfiguracja kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał do skonfigurowania.
1. W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.
1. W liście rozwijanej **hierarchia kategorii** wybierz odpowiednią hierarchię nawigacji kanałów.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W obszarze **Grupa atrybutów** dodaj wszystkie grupy atrybutów, które będą atrybutami globalnymi dla wszystkich węzłów.

Poniższy obraz pokazuje, jak skonfigurować kanał, aby używał hierarchii nawigacji kanału.

![Przykład konfiguracji kanału.](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Metadane ustawiania atrybutu

Ustawienie metadanych atrybutów pozwoli na konfigurację atrybutów w poszczególnych węzłach.

Aby ustawić metadane atrybutów, wykonaj następujące kroki.

1. W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.
1. Dla każdego węzła wybierz **Atrybuty produktu kanału**.
1. Ustaw atrybut **Pokaż atrybut w kanale** na **Tak** i **Może być doprecyzowany** do **Tak**, aby włączyć rafinery na tym kanale.
1. Po skonfigurowaniu każdego węzła w razie potrzeby w **okienku akcji** wybierz przycisk **Zapisz**, aby zapisać.
1. Wybierz **X** w prawym górnym rogu, aby zamknąć ten ekran z powrotem na stronie **Kategorie kanału sprzedaży i atrybuty produktów**.

Poniższy obraz przedstawia przykładowy zbiór atrybutów produktu kanału skonfigurowanych w węźle kategorii kanału.

![Atrybuty kanału w węźle kategorii kanału.](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Opublikuj zmiany

Aby zmiany odniosły skutek, musisz je opublikować.

Aby opublikować zmiany, należy wykonać następujące kroki.

1. W okienku akcji wybierz opcję **Publikowanie aktualizacji kanału**.
1. W okienku **Publikowanie aktualizacji kanału** wybierz **OK**.

Poniższy obraz przedstawia sposób publikowania aktualizacji kanału.

![Publikowanie aktualizacji kanału.](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie hierarchii nawigacji kanału](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]

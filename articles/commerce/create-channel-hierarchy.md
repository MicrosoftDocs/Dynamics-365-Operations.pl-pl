---
title: Tworzenie hierarchii nawigacji kanału
description: W tym artykule opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
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
ms.openlocfilehash: 371c648ccd242c990e095e760e5aa7cc81600395
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869009"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Tworzenie hierarchii nawigacji kanału


[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Hierarchia nawigacji kanałów służy do grupowania i organizowania produktów w kategorie, dzięki czemu można je przeglądać online lub w punkcie sprzedaży (POS).

## <a name="create-a-channel-navigation-hierarchy"></a>Tworzenie hierarchii nawigacji kanału

Aby utworzyć hierarchię nawigacji kanału, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Kategarie nawigacji kanału**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Opis** wprowadź opis.
1. Wybierz opcję **Utwórz**.
1. W okienku akcji naciśnij przycisk **Nowy węzeł kategorii**, aby utworzyć węzeł główny.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Opis** wprowadź opis.
1. W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykładowy węzeł główny.

![Przykładowy węzeł główny.](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Tworzenie węzłów nawigacji kategorii

Aby utworzyć dodatkowe węzły kategorii nawigacji reprezentujące kategorie produktów w kanale, należy wykonać następujące kroki.

1. W okienku nawigacji wybierz węzeł nadrzędny, do którego ma zostać dodana kategoria.
1. W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Opis** wprowadź opis.
1. W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.
1. W polu **Kolejność wyświetlania** wprowadź kolejność wyświetlania (opcjonalnie).
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład ukończonej hierarchii nawigacji kanału.

![Przykładowa hierarchia kanałów.](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Dodawanie produktów do węzłów kategorii

Aby dodać produkty do węzłów kategorii, wykonaj następujące kroki.

1. Wybierz węzeł kategorii.
1. W obszarze **Produkty** wybierz **Dodaj**.
1. Znajdź nowe produkty, których chcesz dodać, używając numeru produktu lub nazwy produktu, a następnie kliknij **OK**.
1. Na okienku akcji wybierz opcję **Zapisz**.

> [!NOTE]
> Dodawanie produktów do węzła znajdującego się w hierarchii nawigacji kanału nie wystarczy, aby produkty były wyświetlane w wybranym kanale, produkty muszą być także w asortymentach kanału. Aby uzyskać więcej informacji o asortymentach, zobacz temat [Zarządzanie asortymentem](assortments.md).

Poniższy obraz przedstawia przykład węzła z dodanymi produktami.

![Produkty dodane do węzła kategorii.](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Dodawanie grup atrybutów produktu do węzłów kategorii

> [!NOTE]
> Grupy atrybutów należy utworzyć przed dodaniem ich do węzła w hierarchii nawigacji kanału.

Aby dodać produkt grupę atrybutów do węzła kategorii, wykonaj następujące kroki.

1. Wybierz węzeł kategorii.
1. W obszarze **Grupa atrybutów produktu** wybierz opcję **Dodaj**.
1. Znajdź grupy atrybutów, które chcesz dodać, a następnie kliknij **OK**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykładowy węzeł z dodanymi grupami atrybutów produktu.

![Grupy atrybutów produktu w węźle.](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie asortymentów](set-up-assortments.md)

[Zarządzanie atrybutami i grupami atrybutów](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

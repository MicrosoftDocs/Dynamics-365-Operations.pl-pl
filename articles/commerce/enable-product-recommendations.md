---
title: Włączanie rekomendacji produktów
description: W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024963"
---
# <a name="enable-product-recommendations"></a>Włączanie rekomendacji produktów

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce. Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Wstępne sprawdzanie rekomendacji

Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów Commerce, którzy przeprowadzili migrację danych do środowiska Azure Data Lake Storage (ADLS). 

Aby uzyskać więcej informacji na temat kroków dotyczących włączania ADLS, zajrzyj do [sposobu włączenia ADLS w środowisku Dynamics 365](enable-ADLS-environment.md).

Ponadto upewnij się, że zostały włączone pomiary RetailSale. Aby dowiedzieć się więcej o tym procesie konfiguracji, przejdź [tutaj.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Włączanie rekomendacji

Aby włączyć rekomendacje produktu, wykonaj następujące czynności.

1. Przejdź do **Handel detaliczny i komercyjny &gt; Rekomendacje produktów &gt; Właściwości rekomendacji**.
1. Na liście udostępnionych parametrów wybierz **Listy rekomendacji**.
1. Ustaw **Włącz rekomendacje** na wartość **Tak**.

![włączanie rekomendacji produktów](./media/enableproductrecommendations.png)

> [!NOTE]
> Ta procedura rozpoczyna proces generowania list rekomendacji produktów. Zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży, może upłynąć kilka godzin (POS) lub w Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Konfigurowanie parametrów listy rekomendacji

Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości. Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy. Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)

Po włączeniu rekomendacji w bac office Commerce, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ. Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Włącz spersonalizowane rekomendacje

Aby uzyskać informacje o spersonalizowanych rekomendacjach produktów, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włącz spersonalizowane rekomendacje](personalized-recommendations.md)

[Dodawanie list rekomendacji produktów do stron](add-reco-list-to-page.md)

[Dodaj panel rekomendacji do urządzeń punktu sprzedaży (POS)](add-recommendations-control-pos-screen.md)

[Omówienie modułu kolekcji produktów](product-collection-module-overview.md)

[Włączanie ADLS w środowisku Dynamics 365](enable-ADLS-environment.md)


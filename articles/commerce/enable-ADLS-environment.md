---
title: Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
author: bebeale
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792614"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.

W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska. Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2.

Ponieważ Azure Data Lake Storage jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.

Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w Azure Data Lake Storage w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.

## <a name="prerequisites"></a>Wymagania wstępne

Klienci muszą mieć Azure Data Lake Storage skonfigurowany w swojej subskrypcji systemu Azure. Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym Azure Data Lake Storage.

Aby uzyskać więcej informacji o Azure Data Lake Storage, zobacz [Oficjalną dokumentację Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Kroki w konfiguracji

W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia Azure Data Lake Storage w środowisku w odniesieniu do zaleceń dotyczących produktów.
Aby uzyskać bardziej szczegółowe omówienie kroków wymaganych do włączenia Azure Data Lake Storage, zapoznaj się z [Udostępnianie magazynu jednostek w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Włączanie Azure Data Lake Storage w środowisku

1. Zaloguj się do portalu back office środowiska.
1. Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**. 
1. Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.
1. Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.
1. Nastepnie wprowadź wymagane informacje:
    1. **Identyfikator aplikacji** // **Wpis tajny aplikacji** // **Nazwa DNS** - wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany tajny wpis Azure Data Lake Storage.
    1. **Tajna nazwa** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą Azure Data Lake Storage.
1. Zapisz zmiany w lewym górnym rogu strony.

Poniższy obraz przedstawia przykład konfiguracji Azure Data Lake Storage.

![Przykładowa konfiguracja Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Przetestuj połączenie Azure Data Lake Storage

1. Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.
1. Przetestuj połączenie z Azure Data Lake Storage za pomocą łącza **Testuj magazyn usługi Azure**.

> [!NOTE]
> Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.

Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.

Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.

1. Wyszukaj **Magazynu jednostek**.
1. Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.
1. Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

Azure Data Lake Storage jest teraz skonfigurowany dla tego środowiska. 

Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Udostępnianie magazynu jednostek w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

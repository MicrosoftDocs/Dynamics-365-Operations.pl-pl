---
title: Włączanie repozytorium Azure Data Lake Storage w środowisku usługi Dynamics 365 Commerce
description: Ten artykuł zawiera instrukcje podłączania rozwiązania Azure Data Lake Storage Gen 2 do magazynu encji środowiska Dynamics 365 Commerce. Jest to krok wymagany przed włączeniem rekomendacji produktów.
author: bebeale
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: d7995e826a838796f714ced2f30220201a157f93
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284753"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Włączanie repozytorium Azure Data Lake Storage w środowisku usługi Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Ten artykuł zawiera instrukcje podłączania rozwiązania Azure Data Lake Storage Gen2 do magazynu encji środowiska Dynamics 365 Commerce. Jest to krok wymagany przed włączeniem rekomendacji produktów.

W rozwiązaniu Dynamics 365 Commerce dane potrzebne do obliczenia rekomendacji, produktów i transakcji są agregowane w magazynie encji środowiska. Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Azure Data Lake Storage Gen2 należącego do klienta.

Po ukończeniu powyższych kroków wszystkie dane klienta w magazynie encji środowiska są automatycznie odzwierciedlane w rozwiązaniu Azure Data Lake Storage Gen 2 klienta. Jeśli funkcje rekomendacji są włączone za pośrednictwem obszaru roboczego Zarządzanie funkcjami w centrali rozwiązania Commerce, stos rekomendacji otrzyma dostęp do tego samego rozwiązania Azure Data Lake Storage Gen2.

Dane klientów są chronione i objęte kontrolą w trakcie całego procesu.

## <a name="prerequisites"></a>Wymagania wstępne

Magazyn encji środowiska Dynamics 365 Commerce musi być połączony z kontem usługi Azure Data Lake Gen Storage Gen2 i usługami towarzyszącymi.

Aby uzyskać więcej informacji o usłudze Azure Data Lake Storage Gen2 i sposobach jej konfigurowania, zobacz [oficjalną dokumentację Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Kroki w konfiguracji

W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia Azure Data Lake Storage Gen2 w środowisku w odniesieniu do zaleceń dotyczących produktów.
Aby uzyskać bardziej szczegółowe omówienie kroków wymaganych do włączenia Azure Data Lake Storage Gen2, zapoznaj się z tematem [Udostępnianie magazynu encji w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Włączanie Azure Data Lake Storage w środowisku

1. Zaloguj się do portalu back office środowiska.
1. Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**. 
1. Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.
1. Nastepnie wprowadź wymagane informacje:
    1. **Identyfikator aplikacji** // **Wpis tajny aplikacji** // **Nazwa DNS** - wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany tajny wpis Azure Data Lake Storage.
    1. **Tajna nazwa** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą Azure Data Lake Storage.
1. Zapisz zmiany w lewym górnym rogu strony.

Poniższy obraz przedstawia przykład konfiguracji Azure Data Lake Storage.

![Przykładowa konfiguracja Azure Data Lake Storage.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Przetestuj połączenie Azure Data Lake Storage

1. Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.
1. Przetestuj połączenie z Azure Data Lake Storage za pomocą łącza **Testuj magazyn usługi Azure**.

> [!NOTE]
> Jeśli którekolwiek z powyższych testów zakończą się niepowodzeniem, potwierdź, że czy wszystkie dodane powyżej informacje usługi KeyVault są poprawne, a następnie spróbuj ponownie.

Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.

Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.

1. Wyszukaj **Magazynu jednostek**.
1. Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.
1. Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem..](./media/exampleADLSConfig2.png)

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

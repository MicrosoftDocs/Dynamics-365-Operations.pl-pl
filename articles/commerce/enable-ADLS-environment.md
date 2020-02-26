---
title: Włączanie ADLS w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
author: bebeale
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 068eb522bd44e02dd31d3337a051691a956637fc
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025272"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>Włączanie ADLS w środowisku Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.

## <a name="overview"></a>Omówienie

W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska. Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2 (ADLS).

Ponieważ ADLS jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.

Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w ADLS w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.

## <a name="prerequisites"></a>Wymagania wstępne

Klienci muszą mieć ADLS skonfigurowany w swojej subskrypcji systemu Azure. Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym ADLS.

Aby uzyskać więcej informacji o ADLS, zobacz [Oficjalną dokumentację systemu ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Kroki w konfiguracji

W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia ADLS w środowisku.

### <a name="enable-adls-in-the-environment"></a>Włączanie ADLS w środowisku

1. Zaloguj się do portalu back office środowiska.
1. Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**. 
1. Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.
1. Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.
1. Nastepnie wprowadź wymagane informacje:
    1. **Identyfikator aplikacji** // **Application Secret** // **Nazwa DNS** -wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany klucz tajny ADLS.
    1. **Secret name** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą ADLS.
1. Zapisz zmiany w lewym górnym rogu strony.

Poniższy obraz przedstawia przykład konfiguracji ADLS.

![Przykładowa konfiguracja ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>Przetestuj połączenie ADLS

1. Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.
1. Przetestuj połączenie z ADLS za pomocą łącza **Testuj magazyn usługi Azure**.

> [!NOTE]
> Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.

Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.

Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.

1. Wyszukaj **Magazynu jednostek**.
1. Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.
1. Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

ADLS jest teraz skonfigurowany dla tego środowiska. 

Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie rekomendacji produktów](enable-product-recommendations.md)

[Dodawanie list rekomendacji produktów do stron](add-reco-list-to-page.md)

[Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach z aplikacją POS](../retail/add-recommendations-control-pos-screen.md?toc=/dynamics365/commerce/toc.json)



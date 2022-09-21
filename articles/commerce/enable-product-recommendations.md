---
title: Włącz rekomendacje produktów
description: W tym artykule wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc1b43fa70e6652d38b1141e2d93cf323f70a756
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460029"
---
# <a name="enable-product-recommendations"></a>Włącz rekomendacje produktów

[!include [banner](includes/banner.md)]

W tym artykule wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce. Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Wstępne sprawdzanie rekomendacji

1. Upewnij się, że masz prawidłową licencję rekomendacji Dynamics 365 Commerce.
1. Upewnij się, że magazyn encji jest połączony z kontem usługi Azure Data Lake Storage Gen2 należącym do klienta. Aby uzyskać więcej informacji, zobacz [Upewnij się, że Azure Data Lake Storage został zakupiony i pomyślnie zweryfikowany w środowisku](enable-ADLS-environment.md).
1. Potwierdź, że konfiguracja tożsamości Azure AD zawiera wpis do Rekomendacji. Poniżej znajduje się więcej informacji dotyczących wykonywania tej akcji.
1. Upewnij się, że dzienne odświeżanie magazynu encji do usługi Azure Data Lake Storage Gen2 zostało zaplanowane. Aby uzyskać więcej informacji, zobacz [Upewnij się, że odświeżanie magazynu jednostek zostało zautomatyzowane. ](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Włącz miary RetailSale dla magazynu encji. Aby uzyskać więcej informacji o konfigurowanie tego procesu, zobacz [Praca z pomiarami](/dynamics365/ai/customer-insights/pm-measures).
1. Upewnij się, że w środowisku skonfigurowano regiony obsługi i przygotowania w obecnie obsługiwanych regionach, jak następuje:

    - **Obsługiwane regiony przygotowania:** UE/US/CA/AU.
    - **Obsługiwane regiony obsługi:** US/CA/AU. Jeśli region obsługi nie pasuje do jednego z istniejących obsługiwanych regionów, usługa rekomendacji wybierze najbliższy obsługiwany region.

Po ukończeniu poszczególnych kroków można włączyć rekomendacje.

> [!NOTE]
> Istnieje znany problem, w którym rekomendacje nie pojawiają się po ukończeniu poniższych kroków. Ten problem jest spowodowany problemami z przepływem danych w środowisku. Jeśli w środowisku nie są wyświetlane wyniki rekomendacji, skonfiguruj alternatywne dane dla usługi rekomendacji, wykonując następujące kroki w celu [Skonfigurowania alternatywnego przepływu danych dla propozycji](set-up-alternate-data-flow.md). Aby wykonać te kroki, musisz mieć uprawnienia administratora systemu Azure. Jeśli będziesz potrzebować pomocy, skontaktuj się z przedstawicielem FastTrack.

## <a name="azure-ad-identity-configuration"></a>Identyfikator konfiguracji Azure AD

Ten krok jest wymagany tylko dla klientów, którzy uruchamiają konfigurację infrastruktury jako usługi (IaaS). Konfiguracja tożsamości usługi Azure AD jest automatyczna w przypadku klientów uruchamiających usługę Azure Service Fabric, ale zalecane jest sprawdzenie, czy ustawienie jest skonfigurowane zgodnie z oczekiwaniami.

### <a name="setup"></a>Konfiguracja

1. W centrali rozwiązania Commerce Headquarters wyszukaj stronę **aplikacji usługi Azure Active Directory**.
1. Sprawdź, czy istnieje wpis **RecommendationSystemApplication-1**. Jeśli wpis nie istnieje, utwórz go, używając następujących informacji:

    - **Identyfikator klienta**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Nazwa**: RecommendationSystemApplication-1
    - **Identyfikator użytkownika**: RetailServiceAccount

1. Zapisz i zamknij stronę. 

## <a name="turn-on-recommendations"></a>Włączanie rekomendacji

Aby włączyć rekomendacje produktu, wykonaj następujące czynności.

1. W module Commerce Headquarters znajdź **Zarządzanie funkcjami**.
1. Opcja **Wszystkie** umożliwia wyświetlenie listy dostępnych funkcji. 
1. W polu wyszukiwania wprowadź **Rekomendacje**.
1. Wybierz funkcję **Rekomendacje produktów**.
1. W okienku właściwości **Rekomendacje produktów** wybierz opcję **Włącz teraz**.

![Włączanie rekomendacji.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - Powyższa procedura rozpoczyna proces generowania list rekomendacji produktów. Może upłynąć kilka godzin zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży (POS) lub w Dynamics 365 Commerce.
> - Ta konfiguracja nie włącza wszystkich funkcji rekomendacji. Do kontrolowania zaawansowanych funkcji, takich jak spersonalizowana rekomendacje, „kupowanie podobnie wyglądających produktów” i „kupowania podobnie opisanych produktów”, są kontrolowane przez dedykowane wpisy zarządzania funkcjami. Aby uzyskać informacje dotyczące włączania tych funkcji w centrali rozwiązania, zobacz [Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md), [Włączanie rekomendacji „kupowania podobnie wyglądających produktów”](shop-similar-looks.md) i [Włączanie rekomendacji „kupowania podobnie opisanych produktów”](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Konfigurowanie parametrów listy rekomendacji

Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości. Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy. Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Uwzględnianie rekomendacji w środowiskach e-commerce

Po włączeniu rekomendacji w centrali Commerce moduły Commerce używane do wyświetlania wyników rekomendacji dla środowisk e-commerce są gotowe do skonfigurowania. Aby uzyskać więcej informacji, zobacz temat [Moduły kolekcji produktów](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)

Po włączeniu rekomendacji w centrali rozwiązania Commerce, panel rekomendacji musi zostać dodany do ekranu kontroli punktu sprzedaży (POS) za pomocą narzędzia układu. Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Włączanie rekomendacji spersonalizowanych

W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja). Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży. Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.

Aby uzyskać informacje o spersonalizowanych rekomendacjach, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Konfigurowanie alternatywnego przepływu danych dla rekomendacji](set-up-alternate-data-flow.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Włączanie rekomendacji dotyczących „kupowania podobnie wyglądających produktów”](shop-similar-looks.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]

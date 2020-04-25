---
title: Włączanie rekomendacji produktów
description: W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
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
ms.openlocfilehash: d38d7b0e98d84e23d7a51c5d8ee65df4a3b9e4a7
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259801"
---
# <a name="enable-product-recommendations"></a>Włączanie rekomendacji produktów

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce. Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Wstępne sprawdzanie rekomendacji

Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów Commerce, którzy przeprowadzili migrację danych za pomocą Azure Data Lake Storage (ADLS). 

Przed włączeniem rekomendacji należy włączyć w biurze zaplecza następujące konfiguracje:

1. Upewnij się, że ADLS został zakupiony i pomyślnie zweryfikowany w środowisku. Aby uzyskać więcej informacji, zobacz [Upewnij się, że ADLS został zakupiony i pomyślnie zweryfikowany w środowisku](enable-ADLS-environment.md).
2. Upewnij się, że odświeżanie magazynu jednostek zostało zautomatyzowane. Aby uzyskać więcej informacji, zobacz [Upewnij się, że odświeżanie magazynu jednostek zostało zautomatyzowane. ](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Potwierdź, że konfiguracja tożsamości Azure AD zawiera wpis do Rekomendacji. Poniżej znajduje się więcej informacji dotyczących wykonywania tej akcji.

Ponadto upewnij się, że zostały włączone pomiary RetailSale. Aby dowiedzieć się więcej o tym procesie konfiguracji, zobacz [Praca z pomiarami](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Identyfikator konfiguracji Azure AD

Ten krok jest wymagany dla wszystkich klientów, którzy uruchamiają strukturę podsieciową jako konfigurację usługi (IaaS). W przypadku klientów korzystających z service fabric (SF) ten krok powinien być automatyczny i zaleca się sprawdzenie, czy ustawienie zostało skonfigurowane zgodnie z oczekiwaniami.

### <a name="setup"></a>Konfiguracja

1. W zapleczu do biura wyszukaj stronę **Aplikacje Azure Active Directory**.
2. Sprawdź, czy istnieje wpis „RecommendationSystemApplication-1”.

Jeśli wpis nie istnieje, dodaj nowy wpis z następującymi informacjami:

- **Identyfikator klienta** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nazwa** - RecommendationSystemApplication-1
- **Identyfikator użytkownika** — RetailServiceAccount

Zapisz i zamknij stronę. 

## <a name="turn-on-recommendations"></a>Włączanie rekomendacji

Aby włączyć rekomendacje produktu, wykonaj następujące czynności.

1. Przejdź do **Handel detaliczny i komercyjny &gt; Rekomendacje produktów &gt; Właściwości rekomendacji**.
1. Na liście udostępnionych parametrów wybierz **Listy rekomendacji**.
1. Ustaw **Włącz rekomendacje** na wartość **Tak**.

![Włączanie rekomendacji](./media/enablepersonalization.png)

> [!NOTE]
> Ta procedura rozpoczyna proces generowania list rekomendacji produktów. Może upłynąć kilka godzin zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży (POS) lub w Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Konfigurowanie parametrów listy rekomendacji

Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości. Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy. Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)

Po włączeniu rekomendacji w bac office Commerce, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ. Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Włączanie rekomendacji spersonalizowanych

W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja). Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży. Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.

Aby uzyskać informacje o spersonalizowanych rekomendacjach, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie ADLS w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


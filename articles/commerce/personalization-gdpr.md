---
title: Wypisz się ze spersonalizowanych rekomendacji produktów
description: W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować z otrzymywania spersonalizowanych rekomendacji w firmie Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 6a64b45e1326673dd84c3c705491c9c100cdd069
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414913"
---
# <a name="opt-out-of-personalized-recommendations"></a>Wypisz się ze spersonalizowanych rekomendacji produktów

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować z otrzymywania spersonalizowanych rekomendacji w firmie Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Podczas tworzenia konta nowi odbiorcy są automatycznie konfigurowani w taki sposób, aby otrzymywać spersonalizowane rekomendacje. Jednak Dynamics 365 Commerce oferuje różne sposoby, aby sprzedawcy mogli zrezygnować z otrzymywania tych zaleceń i ograniczyć przetwarzanie ich danych osobowych. Użytkownicy uwierzytelnieni, którzy zrezygnują z otrzymywania spersonalizowanych rekomendacji, nie będą widzieć już tych spersonalizowanych list. Ponadto wszystkie dane osobowe zbierane w celu personalizacji zostaną usunięte z spersonalizowanych modeli rekomendacji.

Aby uzyskać informacje o spersonalizowanych rekomendacjach produktów, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Sposoby zaimplementowania rezygnacji z usługi

Sprzedawcom udostępniono trzy sposoby zaimplementowania rezygnacji z usługi.

### <a name="opting-out-on-behalf-of-users"></a>Rezygnacja w imieniu użytkowników

W przypadku zarządzania kontami w module zaplecza Commerce, sprzedawcy mogą zrezygnować w imieniu użytkowników.

1. Na stronie głównej zaplecza wyszukaj **wszystkich odbiorców**.
1. Wyszukaj i wybierz odbiorcę, a następnie wybierz skróconą kartę **Sieć sprzedaży**.

    ![Skrócona karta sieci sprzedaży](./media/Disablepersonalizationpart1.png)

1. W obszarze **prywatność** ustaw opcję **Wyłącz personalizację** na **tak**.

    ![Ustawienia prywatności](./media/Disablepersonalizationpart2.png)

1. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="module-based-opt-out-experience"></a>Oparta na module usługa rezygnacji

Detaliści mogą zezwolić uwierzytelnionym użytkownikom na rezygnację z spersonalizowanych rekomendacji. Aby określić to działanie, należy dodać moduł rezygnacji przez użytkownika do stron profilu konta odbiorcy.

### <a name="custom-extensions"></a>Rozszerzenia niestandardowe

Detaliści mogą tworzyć własne rozszerzenia służące do zarządzania niektórymi usługami rezygnacji użytkowników. Aby uzyskać więcej informacji, zobacz [Wywoływanie interfejsów API w usłudze Retail Server](e-commerce-extensibility/call-retail-server-apis.md) i [rozszerzalność kanału online](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Uzyskaj cyfrową kopię spersonalizowanych danych rekomendacji w imieniu uwierzytelnionego użytkownika

Klienci mogą chcieć uzyskać cyfrową kopię swoich danych osobowych, a także wyeksportowanego widoku wyników ich rekomendacji. Jeśli odbiorca zażąda tych informacji, sprzedawca musi utworzyć niestandardowe rozszerzenie, które wywołuje interfejs programowania aplikacji serwera Retail Server (API) i kwerendę dotyczącą pełnych wyników z listy **Wybrane dla Ciebie** na podstawie identyfikatora odbiorcy. Wyniki mogą zostać wyeksportowane w formacie CSV (wartości rozdzielane przecinkami) i udostępniane klientowi.

Poniższy przykład przedstawia sposób, w jaki sprzedawca może wykonać to zadanie.

1. Detalista tworzy niestandardowe rozszerzenie w celu pobrania danych osobistych rekomendacji w imieniu użytkownika. Aby uzyskać informacje na temat tworzenia modułów, klonować istniejące moduły, wywoływać interfejsy API serwera sieci sprzedaży i akcje danych wywołań, należy zapoznać się z tematem [Rozszerzania kanału online](e-commerce-extensibility/overview.md).
2. Rozszerzenie niestandardowe powoduje wywołanie głównej akcji dotyczącej **danych polecanych** do pobrania i przekazuje do niej wymagane informacje na podstawie wymagań listy. W przypadku listy **Wybrane dla Ciebie** rozszerzenie musi przekazać poprawną nazwę listy i identyfikator klienta do akcji danych.

    Jednym ze sposobów utworzenia niestandardowego rozszerzenia jest sklonowanie istniejącego modułu zbierania produktów używanego do zwracania wyników rekomendacji. Przez Klonowanie istniejącego modułu sprzedawca może zmodyfikować istniejący kod i dodać nowy przycisk, który eksportuje wyniki do pliku CSV. Aby uzyskać więcej informacji, zobacz [Sklonuj moduł biblioteki modułów](e-commerce-extensibility/clone-starter-module.md) i [modułu zbierania produktów](product-collection-module-overview.md).

    Aby zapoznać się z pełnym widokiem biblioteki API serwera Retail Server, zobacz [Interfejsy API klienta serwera sieci sprzedaży i odbiorców](dev-itpro/retail-server-customer-consumer-api.md).

3. Po utworzeniu niestandardowego rozszerzenia sprzedawca może eksportować plik CSV wszystkich wyników rekomendacji na podstawie unikatowego identyfikatora klienta uwierzytelnionego użytkownika.
4. Sprzedawca może udostępnić wyeksportowany plik CSV zawierający pełną spersonalizowaną listę zalecanych produktów uwierzytelnionemu użytkownikowi.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)

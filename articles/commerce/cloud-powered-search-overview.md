---
title: Omówienie wyszukiwania w chmurze
description: Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00a3de2515cea341f7529b8cb6cb2caae5e33d22
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414818"
---
# <a name="cloud-powered-search-overview"></a>Omówienie wyszukiwania w chmurze


[!include [banner](includes/banner.md)]

Ten temat zawiera omówienie wyszukiwania w chmurze w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Wykrywanie produktów pomaga zagwarantować klientom szybkie i łatwe wyszukiwanie produktów poprzez przeglądanie kategorii, wyszukiwanie i filtrowanie. Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach.

Klienci są przyzwyczajeni do niemal natychmiastowych czasów reakcji wyszukiwarek internetowych, wyrafinowanych stron e-Commerce, aplikacji społecznościowych, automatycznych sugestii, które pojawiają się podczas wpisywania wyszukiwanych haseł, fasetowanej nawigacji i wyróżniania. Jeśli klienci nie mogą znaleźć produktu, którego szukają wystarczająco szybko w jednym sklepie e-Commerce, nie zawahają się pójść do innego sklepu e-Commerce.

Możliwość wykrywania produktów w chmurze w Dynamics 365 Commerce ułatwia detalistom dalsze zwiększenie częstotliwości przechowywania i kursów wymiany między wszystkimi kanałami, zarówno kanałami e-Commerce i kanałami punktu sprzedaży (POS)

W wyszukiwaniu Dynamics 365 Commerce ulepszono możliwości pomagające detalistom w osiągnięciu lepszej wykrywalności produktów. Jednocześnie funkcje te zapewniają skalowalność i wydajność, które są wymagane w przypadku ruchu w e-Commerce.

## <a name="browse-and-search"></a>Przeglądaj i szukaj

Trafność i wydajność wyszukiwania są kluczowymi czynnikami w doświadczeniu wielokanałowym, ponieważ odkrywanie produktu polega przede wszystkim na funkcji wyszukiwania w zakresie wyszukiwania informacji i nawigacji treści. Skuteczne i wydajne przeglądanie i wyszukiwanie pomaga zwiększyć konwersję.

Na poniższej ilustracji przedstawiono przykład typowej funkcji przeglądania i wyszukiwania.

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Szlifowana nawigacja i podsumowanie wyboru 

Nawigacja fasetowa pomaga klientom łatwiej przeglądać zawartość, umożliwiając im filtrowanie według rafinerii powiązanych z warunkami w zestawie terminów. Po wybraniu i zastosowaniu rafinerów przez klienta wyświetlane jest podsumowanie wybranych opcji. 

Korzystając z nawigacji fasetowej, możesz skonfigurować różne rafinery dla różnych terminów w zestawie terminów, bez konieczności tworzenia dodatkowych stron. 

Poniższa ilustracja pokazuje przykład, w którym podczas wyszukiwania używana jest nawigacja fasetowa.

![Podsumowanie wyboru](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Immersyjne autosugerowanie

Bieżąca funkcja autosugerowania pokazuje słowa kluczowe, które wyzwalają wyszukanie odpowiedniego słowa kluczowego. Ze względu na nowe ulepszenia w Dynamics 365 Commerce klienci mogą często wykrywać łącza do produktów, zanim zakończą one wpisywanie.

Dynamics 365 Commerce obsługuje także funkcje dotyczące słów kluczowych w różnych kategoriach. Dzięki tej funkcji klienci widzą liczbę słów kluczowych w różnych kategoriach i uruchamiają wyszukiwanie słowa kluczowego w innych kategoriach.

Na poniższej ilustracji pokazano przykład, na którym jest używana funkcja automatycznego sugerowania.

![immersyjne autosugerowanie](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Sortuj

Ulepszone sortowanie w Dynamics 365 Commerce umożliwia odbiorcom sortowanie, wyszukiwanie i przeglądanie wyników wyszukiwania oraz modyfikowanie ich według kryteriów, takich jak cena, nazwa produktu i numer produktu. Wyniki mogą również posłużyć do sortowania produktów w zależności od tego, czy produkt jest nowością, bestsellerem czy został niedawno dodany.

>[!NOTE]
>Te możliwości wyszukiwania z wykorzystaniem chmury są dostępne począwszy od wersji 10.0.8. Upewnij się, że w menu **Parametry Commerce > Konfigurowanie parametrów** istnieje wpis o wartości „true” dla parametru „ProductSearch.UseAzureSearch”. 
![Parametry konfiguracji dla wyszukiwania z wykorzystaniem chmury](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Domyślna strona docelowa kategorii i strona wyników wyszukiwania – omówienie](category-search-page-overview.md)

[Zarządzanie metadanymi SEO](manage-seo-metadata.md)

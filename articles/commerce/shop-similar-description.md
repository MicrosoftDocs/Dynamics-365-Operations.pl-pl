---
title: Włączanie rekomendacji dotyczących „kupowania podobnie opisanych produktów”
description: W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bsokolov
ms.date: 01/13/2021
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
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ce01ef1d4b916d955685b4d01dafd3d54d6fcebd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795412"
---
# <a name="enable-shop-similar-description-recommendations"></a>Włączanie rekomendacji dotyczących „kupowania produktów z podobnym opisem”

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.

Funkcja rekomendacji „kup podobne” w Dynamics 365 Commerce wykorzystuje sztuczną inteligencję i uczenie maszynowe (AI-ML) do dostarczania rekomendacji dla produktów, które mają opisy podobne do tego, czego szuka klient. Udostępniając rekomendacje „kupuj o podobnym opisie” dla wszystkich kanałów sprzedaży detalicznej w usłudze Commerce, sprzedawcy pomóc klientom łatwo znaleźć to, czego szukają.

Funkcjonalność rekomendacji „kupuj podobny opis” wykorzystuje nazwę produktu i opis produktów nasiennych, aby znaleźć i polecić podobne produkty w katalogu produktów sprzedawcy.

Rekomendacje „Kup podobnie opisane” są dostępne zarówno w punktach sprzedaży (POS), jak i w rozwiązań handlu elektronicznego.

## <a name="example-scenarios"></a>Przykładowe scenariusze

W poniższych przykładach przedstawiono typy rekomendacji, które może dostarczać funkcja „kupuj podobne”:

- Klient ogląda parę okularów w rogowej oprawie w stylu retro i otrzymuje zestaw zaleceń dotyczących innych okularów o podobnym wyglądzie w kontekście branży detalicznej.
- Klient korzysta z zaleceń „kupuj podobne”, aby odkryć aromaty kawy, które są podobne do smaku, który wcześniej kupił od sprzedawcy.

## <a name="set-up-shop-similar-description-recommendations"></a>Włączanie rekomendacji dotyczących „kupowania podobnie opisanych produktów”

Zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników Commerce, którzy przeprowadzili migrację magazynu do Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim rekomendacje „kupuj podobne” będą mogły być wyświetlane klientom, musisz spełnić następujące wymagania wstępne:

- [Włącz rekomendacje produktów](enable-product-recommendations.md) w Commerce Headquarter.
- Upewnij się, że serwer multimediów obsługuje połączenia HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Włącz funkcję rekomendacji „kupowania podobnie opisanych produktów”

Aby włączyć funkcję rekomendacji „Kup podobne” w centrali Commerce, wykonaj następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** z listy dostępnych funkcji wyszukaj i wybierz pozycję **Kup podobnie opisane**.
1. W okienku po prawej stronie włącz pozycję **Włączanie**.

> [!NOTE]
> Po włączeniu tej funkcji system zaczyna generować listy rekomendacji produktów. Może minąć nawet jeden dzień, zanim listy te staną się dostępne i widoczne w Internecie i na terminalach POS.
>
> Wyłączenie tej funkcji nie wpływa na inne typy rekomendacji produktów. Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Dodawanie przycisku Opis sklepu podobnego do stron szczegółów produktu

Po włączeniu funkcji rekomendacji „kupuj podobne” w centrali Commerce możesz dodać przycisk **Kupuj podobne** do pola zakupu na dowolnej stronie szczegółów produktu (PDP). Klient, który wybierze ten przycisk, zostaje przeniesiony na specjalną stronę **Kup podobnie opisane**, która zwraca wizualnie podobne produkty. W tym celu odbiorca może wykorzystać selektory do dalszego filtrowania produktów.

Aby dodać przycisk **Kup podobnie opisane** do stron PDP za pomocą narzędzia do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Otwórz istniejącą stronę konstruktora witryn zawierającą moduł pola zakupu.
1. W okienku nawigacji po lewej stronie zaznacz moduł pola zakupu.
1. W prawym okienku nawigacji zaznacz pole wyboru **Włącz łącze kup podobnie opisane**.
1. Wybierz opcję **Zapisz**.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować. Po opublikowaniu strony PDP będzie zawierała przycisk **Kup podobnie opisane**.

Na poniższej ilustracji przedstawiono pole wyboru **Włącz łącze kup podobnie opisane** i **Kup podobnie opisane** na przykładowej PDP w konstruktorze witryn.

![Włącz pole wyboru Link do podobnego opisu sklepu i przycisk Kup podobny opis na PDP w narzędziu do tworzenia witryn](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji dotyczących „kupowania podobnie wyglądających produktów”](shop-similar-looks.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
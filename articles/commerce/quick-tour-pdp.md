---
title: Omówienie stron szczegółów produktów
description: W tym artykule omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/23/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7b7630a15f98da4a1454f7c9b0d3501d4f035649
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884292"
---
# <a name="product-details-pages-overview"></a>Omówienie stron szczegółów produktów

[!include [banner](includes/banner.md)]

W tym artykule omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.

PDP dostarcza szczegółowych informacji o produkcie, a klienci wybierają opcje produktu, takie jak rozmiar, styl i kolor. PDP powinien prezentować wszystkie informacje o produktach, których wymaga klient w celu podjęcia decyzji o zakupie.

Na poniższe ilustracji pokazano przykład PDP.

![Przykład strony ze szczegółami dotyczącymi produktu.](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Moduły nagłówka i stopki

U góry PDP znajduje się nagłówek pokazujący wszystkie kategorie produktów i inne strony, które sprzedawca chce przejrzeć. Dolna część strony zawiera stopkę zawierającą szybkie łącza do różnych artykułów, które mogą być przedmiotem zainteresowania odbiorców.

## <a name="buy-box-module"></a>Moduł pola zakupu

Najważniejszym modułem układu PDP jest moduł pudełka zakupu, który jest wyświetlany jako pierwszy element w sekcji głównej strony. W module pole zakupu są wyświetlane ważne informacje dotyczące produktu, takie jak nazwa produktu, opis produktu, cena produktu, obrazy produktów i oceny produktów.

Moduł pola zakupu pozwala odbiorcy wybrać opcje produktu (np. rozmiar, styl i kolor) i dodać produkt do koszyka. Umożliwia również kupowanie produktu w trybie online i pobieranie go w sklepie. Moduł kupowanie w trybie online i pobierz w sklepie używa integracji z interfejsami programowania aplikacji (API) mapy Bing w celu znalezienia bliskich sklepów lub sklepów w innej lokalizacji określanej przez odbiorcę

Moduł pola zakupu wymaga identyfikatora produktu. Ten identyfikator jest pochodną z kontekstu strony. Jeśli do strony, w której kontekst strony nie zawiera identyfikatora produktu, zostanie dodany moduł pola zakupu, informacje te nie zostaną poprawnie zachowane.

## <a name="product-specifications-module"></a>Moduł specyfikacji produktu

Moduł specyfikacji produktu może służyć do prezentowania dodatkowych szczegółów dotyczących produktu. Te szczegóły są pobierane z atrybutów produktów w Commerce. Moduł specyfikacje produktu pokazuje każdy atrybut, w którym właściwość **widoczne** ma wartość **prawda**. Do pobrania atrybutów produktu wymagana jest nazwa produktu.

## <a name="recommendations-module"></a>Moduł rekomendacji

Najważniejszym modułem układu PDP jest moduł rekomendacji. Podczas przeglądania produktów przez użytkowników należy przedstawić im więcej opcji, dzięki czemu mogą one znaleźć poprawny produkt i dokonać zakupu. Rekomendacje pomagają klientom w łatwejszym odnajdywaniu powiązanych treści i w dalszym ciągu kupować.

Dostępne są różne typy list rekomendacji:

- Lista **Klientom podoba się również** jest oparta na nauczeniu maszynowym. Zawiera ona historię transakcji innych odbiorców w celu dostarczenia zaleceń. Ta lista jest generowana przez usługę rekomendacji i przypomina listę „Klienci, krórzy kupili ten produkt, kupili również...”. Do wygenerowania tej listy wymagany jest identyfikator produktu.
- Listę **pokrewną** można skonfigurować dla produktu w sieci Commerce. Na przykład w przypadku brązowej skórzanej torebki można skonfigurować więcej torebek skórzanych lub zaprojektowanych do celów związanych z podróżą dla powiązanej listy. Inne typy list pokrewnych, takie jak **akcesoria** i **podobne do tego**, można również konfigurować w module Commerce. Do wygenerowania tej listy wymagany jest identyfikator produktu. W związku z tym, jeśli w kontekście strony zostanie dodany do strony głównej, lista nie będzie zawierała identyfikatora produktu.
- Algorithmically wygenerowane listy rekomendacji, takie jak **Trendy**, **Bestsellery** i **Nowości**, mogą być używane na PDPs. Chociaż te listy mogą nie być bezpośrednio związane z produktem PDP, są one kolejnym sposobem ułatwienia klientom znalezienia produktów, które mogą je zainteresować. Te typy list nie wymagają identyfikatora produktu. Są to listy ogólne, które są generowane na podstawie wzorców zakupów w witrynie.
- Listy redakcyjne są ręcznie wyselekcjonowane. Na przykład detalista może zdecydować o ręcznym zaprezentowania list produktów, które chce prezentować.

## <a name="ratings-and-reviews-modules"></a>Moduły ocen i recenzji

Do wyświetlania i dodawania recenzji można używać trzech modułów:

- **Recenzje** — Moduł zawiera oceny i przeglądy, które zostały udostępnione przez innych odbiorców. Odbiorcy mogą sortować i filtrować Recenzje. Do tego modułu Klienci ci powinni również zaznaczyć, czy Recenzje są pomocne, czy nie, i zgłaszać problemy.
- **Napisz recenzję** — ten moduł umożliwia pisanie własnych przeglądów produktu.
- **Histogram klasyfikacji** — ten moduł zawiera histogram pokazujący trend klasyfikacji produktu.

Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie ocen i recenzji](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Moduły marketingu

Jeśli zawartość marketingowa jest unikatowa dla określonego produktu, do PDP można dodać dowolny moduł marketingowy. Moduły marketingowe można dodawać do PDP przez „wzbogacanie” strony. Więcej informacji zawiera sekcja [wzbogacanie strony produktu](enrich-product-page.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie strony głównej](quick-tour-home-page.md)

[Omówienie stron koszyka i realizacji zamówienia](quick-tour-cart-checkout.md)

[Omówienie stron zarządzania kontem](quick-tour-account-management.md)

[Wzbogacanie strony szczegółów na temat produktu](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Omówienie stron szczegółów produktów
description: W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3b02d50adbfcda27d590bcb87fd9669d67d4a01c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697872"
---
# <a name="overview-of-product-details-pages"></a>Omówienie stron szczegółów produktów

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

PDP dostarcza szczegółowych informacji o produkcie, a klienci wybierają opcje produktu, takie jak rozmiar, styl i kolor. PDP powinien prezentować wszystkie informacje o produktach, których wymaga klient w celu podjęcia decyzji o zakupie.

Na poniższe ilustracji pokazano przykład PDP.

![Przykład strony ze szczegółami dotyczącymi produktu](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Moduły nagłówka i stopki

U góry PDP znajduje się nagłówek pokazujący wszystkie kategorie produktów i inne strony, które sprzedawca chce przejrzeć. Dolna część strony zawiera stopkę zawierającą szybkie łącza do różnych tematów, które mogą być przedmiotem zainteresowania odbiorców.

## <a name="buy-box-module"></a>Moduł pola zakupu

Najważniejszym modułem układu PDP jest moduł pudełka zakupu. Dlatego jest to pierwszy element w sekcji głównej strony. Moduł pudełka z kupowaniem jest modułem kontenera i obsługuje kilka modułów zawierających najważniejsze informacje o produkcie. Informacje te obejmują nazwę produktu, obrazy produktów, opis, cenę i oceny produktów.

Moduł pola zakupu pozwala odbiorcy wybrać opcje produktu (np. rozmiar, styl i kolor) i dodać produkt do koszyka. Umożliwia również kupowanie produktu w trybie online i pobieranie go w sklepie. Moduł kupowanie w trybie online i pobierz w sklepie używa integracji z interfejsami programowania aplikacji (API) mapy Bing w celu znalezienia bliskich sklepów lub sklepów w innej lokalizacji określanej przez odbiorcę

Moduł pola zakupu wymaga identyfikatora produktu. Ten identyfikator jest pochodną z kontekstu strony. Jeśli do strony, w której kontekst strony nie zawiera identyfikatora produktu, zostanie dodany moduł pola zakupu, informacje te nie zostaną poprawnie zachowane.

## <a name="product-specifications-module"></a>Moduł specyfikacji produktu

Moduł specyfikacji produktu może służyć do prezentowania dodatkowych szczegółów dotyczących produktu. Te szczegóły są pobierane z atrybutów produktów w Dynamics 365 Retail. Moduł specyfikacje produktu pokazuje każdy atrybut, w którym właściwość **widoczne** ma wartość **prawda**. Do pobrania atrybutów produktu wymagana jest nazwa produktu.

## <a name="recommendations-module"></a>Moduł rekomendacji

Najważniejszym modułem układu PDP jest moduł rekomendacji. Podczas przeglądania produktów przez użytkowników należy przedstawić im więcej opcji, dzięki czemu mogą one znaleźć poprawny produkt i dokonać zakupu. Rekomendacje pomagają klientom w łatwejszym odnajdywaniu powiązanych treści i w dalszym ciągu kupować.

Dostępne są różne typy list rekomendacji:

- Lista **Klientom podoba się również** jest oparta na nauczeniu maszynowym. Zawiera ona historię transakcji innych odbiorców w celu dostarczenia zaleceń. Ta lista jest generowana przez usługę rekomendacji i przypomina listę „Klienci, krórzy kupili ten produkt, kupili również...”. Do wygenerowania tej listy wymagany jest identyfikator produktu.
- Listę **pokrewną** można skonfigurować dla produktu w sieci Retail. Na przykład w przypadku brązowej skórzanej torebki można skonfigurować więcej torebek skórzanych lub zaprojektowanych do celów związanych z podróżą dla powiązanej listy. Inne typy list pokrewnych, takie jak **akcesoria** i **podobne do tego**, można również konfigurować w module Retail. Do wygenerowania tej listy wymagany jest identyfikator produktu. W związku z tym, jeśli w kontekście strony zostanie dodany do strony głównej, lista nie będzie zawierała identyfikatora produktu.
- Algorithmically wygenerowane listy rekomendacji, takie jak **Trendy**, **Bestsellery** i **Nowości**, mogą być używane na PDPs. Chociaż te listy mogą nie być bezpośrednio związane z produktem PDP, są one kolejnym sposobem ułatwienia klientom znalezienia produktów, które mogą je zainteresować. Te typy list nie wymagają identyfikatora produktu. Są to listy ogólne, które są generowane na podstawie wzorców zakupów w witrynie.
- Listy redakcyjne są ręcznie wyselekcjonowane. Na przykład detalista może zdecydować o ręcznym zaprezentowania list produktów, które chce prezentować.

## <a name="ratings-and-reviews-module"></a>Moduły ocen i recenzji

Moduł oceny i Recenzje zawiera oceny i przeglądy, które zostały udostępnione przez innych odbiorców. Umożliwia także wpisywanie przez odbiorcę własnego przeglądu produktu. Ponadto zawiera on histogram przedstawiający trend klasyfikacji produktu. Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie ocen i recenzji](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Moduły marketingu

Jeśli zawartość marketingowa jest unikatowa dla określonego produktu, do PDP można dodać dowolny moduł marketingowy. Moduły marketingowe można dodawać do PDP przez „wzbogacanie” strony. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie strony głównej](quick-tour-home-page.md)

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Omówienie stron koszyka i realizacji zamówienia](quick-tour-cart-checkout.md)

[Omówienie stron zarządzania kontem](quick-tour-account-management.md)

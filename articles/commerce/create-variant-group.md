---
title: Utwórz grupę wariantów
description: W tym temacie opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0462958d8225de145a8d886b096f96cd3f2cb5c5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799548"
---
# <a name="create-a-variant-group"></a>Tworzenie grupy wariantów


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Dynamics 365 Commerce obsługuje wiele wariantów produktów. Doskonale nadaje się do konfigurowania grup wariantów dla różnych kategorii produktów. Można na przykład utworzyć grupę rozmiarów dla koszulki o rozmiarach bardzo małych, małych, średnich, dużych i bardzo dużych, lub utworzyć grupę kolorów, tak aby obejmowała wszystkie dostępne kolory produktu. Przed dodaniem produktów należy dodać grupy wariantów.

W tym temacie zostanie utworzona i skonfigurowana grupa rozmiarów. Podobne procedury mogą służyć do dodawania i konfigurowania grup stylów oraz grup kolorów.

## <a name="create-a-size-group"></a>Tworzenie grupy rozmiarów

Aby utworzyć grupę rozmiarów, należy wykonać poniższe kroki.
 
1. W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Grupy wariantów \> Grupy rozmiarów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Grupa rozmiarów** wpisz unikatową nazwę grupy rozmiarów.
1. W razie potrzeby w polu **Opis** wprowadź opis.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="add-attributes-to-the-size-group"></a>Dodaj atrybuty do grupy rozmiarów

Aby dodać atrybuty do grupy rozmiarów, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Grupy wariantów \> Grupy rozmiarów**
1. W okienku nawigacji kategorii wybierz grupę rozmiarów.
1. W obszarze **Wiersze grupy rozmiarów** wybierz **Dodaj**.
1. W polu **Grupa rozmiarów** wpisz ciąg reprezentujący rozmiar (na przykład „XL”).
1. W polu **Nazwa rozmiaru** wprowadź nazwę rozmiaru (na przykład „ekstra duże”).
1. W polu **Waga uzupełnienia** wprowadź liczbę reprezentującą wagę uzupełnienia.
1. W polu **numer w kodzie kreskowym** wprowadź liczbę reprezentującą kod kreskowy.
1. W polu **Kolejność wyświetlania** wprowadź numer kolejności wyświetlania.
1. Po zakończeniu dodawania rozmiarów wybierz opcję **Zapisz** w okienku akcji.

Poniższy obraz przedstawia przykład konfiguracji przypisania grupy rozmiary dla „rozmiary koszulek codziennych”.

![Tworzenie grupy rozmiarów](media/create-variant-group.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie informacji o produktach](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Konfigurowanie produktów sprzedaży detalicznej](set-up-retail-products.md)

[Wymiary produktu](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
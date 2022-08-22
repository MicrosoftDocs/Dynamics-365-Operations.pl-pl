---
title: Tworzenie grupy wariantów
description: W tym artykule opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
ms.openlocfilehash: 507076259c2d9dfe97a0e24d253b5ac0a8325fe2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270108"
---
# <a name="create-a-variant-group"></a>Tworzenie grupy wariantów


[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Dynamics 365 Commerce obsługuje wiele wariantów produktów. Doskonale nadaje się do konfigurowania grup wariantów dla różnych kategorii produktów. Można na przykład utworzyć grupę rozmiarów dla koszulki o rozmiarach bardzo małych, małych, średnich, dużych i bardzo dużych, lub utworzyć grupę kolorów, tak aby obejmowała wszystkie dostępne kolory produktu. Przed dodaniem produktów należy dodać grupy wariantów.

W tym artykule zostanie utworzona i skonfigurowana grupa rozmiarów. Podobne procedury mogą służyć do dodawania i konfigurowania grup stylów oraz grup kolorów.

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

![Tworzenie grupy rozmiarów.](media/Size-Groups.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie informacji o produktach](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Konfigurowanie produktów handlu detalicznego](set-up-retail-products.md)

[Wymiary produktu](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

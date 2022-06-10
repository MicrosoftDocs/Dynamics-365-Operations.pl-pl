---
title: Moduł karty
description: W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 104fb57cfdcd96a0da50899c0eac576074282017
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780621"
---
# <a name="tab-module"></a>Moduł tabularny

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły karty i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły kart są modułami przypominającymi kontenery, które służą do organizowania informacji na stronie witryny na kartach. Można ich używać na dowolnej stronie, na której należy przedstawić informacje na kartach.

W każdym module karty można dodać jeden lub więcej modułów pozycji karty. Każdy moduł karty reprezentuje pojedynczą kartę. W każdym module pozycji karty można dodać jeden lub więcej modułów. Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji karty.

Poniższy obraz pokazuje przykład modułu karty na stronie witryny. W tym przykładzie wybrano kartę **Wysyłka**.

![Przykład modułu karty.](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Właściwości modułu karty

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek | Tekst | Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu kart. |
| Aktywny indeks karty | Identyfikator | Właściwość ta określa kartę, która powinna być domyślnie aktywna podczas ładowania strony. Jeśli nie zostanie podana żadna wartość, domyślnie jest aktywna pierwsza pozycja karty. |

## <a name="tab-item-module-properties"></a>Właściwości modułu pozycji karty

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nazwa | Tekst | Ta właściwość określa tekst tytułu dla modułu pozycji karty. |

## <a name="add-a-tab-module-to-a-page"></a>Dodawanie modułu karty do strony

Aby dodać moduł karty do strony i ustawić właściwości, wykonaj następujące kroki.

1. Użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Strona zasad sklepu**.
1. W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Karta** i wybierz przycisk **OK**.
1. W okienku właściwości modułu kart wybierz pozycję **Nagłówek** obok symbolu ołówka.
1. W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź tekst nagłówka (np. **Zasady**). Następnie wybierz opcję **OK**.
1. W gnieździe **Karta** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Element karty** i wybierz przycisk **OK**.
1. W okienku właściwości modułu pozycji kart w obszarze **Tytuł** wprowadź tekst tytułu (np. **Dostawa**).
1. W gnieździe **Pozycja karty** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.
1. W okienku właściwości modułu blok tekstu pod **Tekst sformatowany** wprowadzić akapit tekstu..
1. W gnieździe **Karta** dodaj kilka dodatkowych modułów z kartami z tytułami. W każdym module pozycji karty należy dodać moduł bloku tekstu z zawartością.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Na stronie zostanie wyświetlona karta zawierająca moduły pozycji karty, która zawiera dodaną zawartość.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł typu accordion](add-accordion.md)

[Moduł bloku tekstu](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

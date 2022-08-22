---
title: Wzbogacanie strony produktu
description: W tym artykule opisano sposób wzbogacania strony produktu w Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f01dcc2518fe861339b4984522582ed3de7aa6ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282142"
---
# <a name="enrich-a-product-page"></a>Wzbogacanie strony produktu

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób wzbogacania strony produktu w Microsoft Dynamics 365 Commerce.

Domyślnie witryna używa strony ogólnej do wyświetlania danych produktu. Ta strona zawiera podstawowe informacje o produkcie i formantach, które są wymagane do jego sprzedaży. Można jednak uzupełnić informacje pochodzące z Commerce Scale Unit dodatkowymi obrazami lub tekstami dla określonego produktu. Ten proces jest znany jako wzbogacanie strony produktu.

W wielu przypadkach użytkownik chce użyć konkretnej zawartości dodatkowej w odniesieniu do produktów. Po przejściu do **Handel detaliczny i komercyjny** w narzędziu autorskim zostanie wyświetlona lista produktów z kanału przypisanego do danego oddziału. Na tej liście **Wzbogacone** kolumna wskazuje, czy dana strona produktu została wzbogacona. Jeśli w kolumnie zostanie wyświetlony znacznik wyboru, dla produktu istnieje wzbogacona strona produktu Jeśli żaden znacznik wyboru nie zostanie wyświetlony, dla produktu zostanie użyta domyślna strona produktu i zawartość. Można przeglądać zarówno wzbogacone, jak i niewzbogacone strony produktu, wybierając nazwę produktu z listy.

## <a name="enrich-a-product-page"></a>Wzbogacanie strony produktu

Aby wzbogacić stronę produktu, należy wykonać następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie zaznacz **Produkty**.
1. Wybierz produkt, który nie ma wzbogaconej strony produktu.
1. W okienku akcji wybierz pozycję **Wzbogać stronę produktu**.
1. Zaznacz element **Szablon PDP** i kliknij przycisk **OK**.
1. W konspekcie strony z lewej strony rozwiń gniazdo **Główne**.
1. Wybierz przycisk wielokropka (**...**) dla gniazda **Główne**, a następnie wybierz opcję **Dodaj moduł**.
1. Zaznacz element **Kontener 2** i kliknij przycisk **OK**.
1. Wybierz przycisk wielokropka dla **Kontenera 2**, a następnie wybierz opcję **Dodaj moduł**.
1. Zaznacz element **Funkcja** i kliknij przycisk **OK**.
1. W okienku właściwości z prawej strony w polu **tekst sformatowany** wprowadź zaktualizowany opis produktu.
1. W polu **Nagłówek** wprowadź tekst nagłówka, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. W polu **Komentarze** wprowadź **Wzbogacono produkt**, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd wzbogaconej strony produktu. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Wzbogacanie strony docelowej kategorii
description: W tym artykule opisano wzbogacanie stron kategorii w Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: e3397ffee9b32f3d3efedea38255f88daee5233c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282169"
---
# <a name="enrich-a-category-landing-page"></a>Wzbogacanie strony docelowej kategorii

[!include [banner](includes/banner.md)]

W tym artykule opisano wzbogacanie stron kategorii w Dynamics 365 Commerce.

W handlu jest dostępna domyślna strona początkowa kategorii używana podczas wyświetlania danych kategorii. Domyślna strona kategorii zawiera wymagane elementy, takie jak rafinerie, skategoryzowane lokowanie produktu, opcje sortowania, podsumowanie wyboru i elementy sterujące stronicowaniem. 

Jednak zamiast korzystania z domyślnej strony kategorii można użyć strony docelowej kategorii „wzbogacone”, która ma więcej zawartości i bardziej konkretne elementy. Typowe wzbogacenie może obejmować dodawanie treści marketingowych specyficznych dla kategorii do strony kategorii. Ta zawartość może zawierać rozmieszczenie produktów z różnych kategorii dla celów sprzedaży krzyżowej, list redakcyjnych, obrazów, filmów wideo i innego tekstu. Można zmodyfikować domyślną stronę kategorii lub zdefiniować inną stronę kategorii dla danej kategorii.

![Wzbogacona strona docelowa kategorii.](./media/CategoryLandingPages.png)

W konstruktorze witryn Commerce strona **Produkty** w narzędziu autorskim zawiera listę kategorii z kanału przypisanych do oddziału. Jeśli **Wzbogacone** stan jest zaznaczony dla strony kategorii, dana strona kategorii została wzbogacona. W przeciwnym razie używana jest domyślna strona kategorii i zawartość dla danej kategorii. Możesz wyświetlić podgląd zarówno kategorii wzbogaconej, jak i nie wzbogaconej kategorii, wybierając nazwę kategorii.

Aby wzbogacić stronę kategorii, należy wykonać następujące czynności.

1. Na stronie **Produkty** wybierz nazwę kategorii, dla której chcesz wzbogacić stronę kategorii. Domyślna strona kategorii dla wybranej kategorii jest otwierana w edytorze stron.
2. Wybierz **Wzbogać stronę kategorii**.
3. Wybierz szablon dla wzbogaconej strony kategorii. W przypadku wprowadzania tylko drobnych zmian można wybrać domyślną stronę kategorii. Alternatywnie można wybrać określony szablon strony kategorii. Po wybraniu szablonu zostanie otwarty Edytor stron, a wybrany szablon zostanie użyty do utworzenia nowej strony kategorii dla wybranej kategorii. Strona jest wyewidencjonowana dla Ciebie i teraz możesz wprowadzić zmiany.

> [!NOTE]
> Moduły korzystające z danych specyfikacji kategorii używają danych z wybranej kategorii. Ustawienia wybranego szablonu decydują o zmianach, które można wprowadzić w tym szablonie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

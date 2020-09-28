---
title: Moduł Menu nawigacji
description: W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761415"
---
# <a name="navigation-menu-module"></a>Moduł Menu nawigacji

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Głównym celem modułów menu nawigacji jest umożliwienie użytkownikom witryny przeglądania produktów i stron witryny zgodnie z hierarchią nawigacji kanału zdefiniowaną w centrali Dynamics 365 Commerce. Elementy skonfigurowane w module menu nawigacji są wyświetlane jako nawigacja nagłówka oddziału. Moduły menu nawigacji obsługują także statyczne elementy menu, które łączą się z innymi stronami w witrynie handlu elektronicznego.

Moduł menu nawigacji można dodać do modułu nagłówka strony. W motywie Fabrikam w menu nawigacji domyślnie są wyświetlane dwa poziomy. W motywie Starter w menu nawigacji domyślnie są wyświetlane trzy poziomy. Aby zmienić liczbę poziomów, na motywie jest wymagane rozszerzenie widoku.

Na poniższej ilustracji pokazano przykład menu nawigacji dla witryny Fabrikam z dwoma poziomami hierarchii kategorii i pewnymi statycznymi elementami menu.
![Przykład modułu menu nawigacji](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Moduł Menu nawigacji — właściwości

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Źródło                  | **Handel detaliczny**, **Ręczne tworzenie**, **Tworzenie detaliczne i ręczne** | Wartość **Detaliczna** umożliwia wyświetlanie hierarchii nawigacji kanału w menu nawigacji z poziomu modułu Commerce Headquarter. **Tworzenie ręczne** umożliwia analizę statycznych elementów menu. Ustawienie wartości **Tworzenie ręczne i detaliczne** umożliwia stosowanie kombinacji obu typów. |
| Wyświetlanie obrazów kategorii | **Prawda** lub **Fałsz**    | Po włączeniu tej właściwości w menu nawigacji są wyświetlane obrazy kategorii zdefiniowane w module Commerce Headquarter dla każdej kategorii. Dodane do modułu Commerce Release 10.0.14. |
| Statyczny element menu| Tablica wartości| Statyczne elementy menu, które kojarzą nazwę elementu menu z łączem do statycznej strony witryny. Można utworzyć elementy menu poniżej innych elementów menu. Domyślnie menu statyczne pojawia się na poziomie głównym i zostanie dołączone do hierarchii nawigacji kanału, jeśli taka istnieje. |

Na poniższej ilustracji pokazano przykład obrazu kategorii wyświetlanego w menu nawigacji witryny Fabrikam.
![Przykład modułu menu nawigacji z obrazami kategorii](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Dodawanie modułu menu nawigacji do modułu nagłówka

Aby uzyskać szczegółowe informacje na temat dodawania modułu menu nawigacji do modułu nagłówka, skorzystaj z [modułu nagłówka](author-header-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Zgodność z plikami cookie](cookie-compliance.md)

[Moduł nagłówka](author-header-module.md)

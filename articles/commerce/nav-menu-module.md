---
title: Moduł Menu nawigacji
description: W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "4415077"
---
# <a name="navigation-menu-module"></a>Moduł Menu nawigacji

[!include [banner](includes/banner.md)]

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
| Włącz wielopoziomowe menu nawigacji | **Prawda** lub **Fałsz** | Po włączeniu tej właściwości menu nawigacji może zawierać wiele poziomów hierarchii nawigacji. Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.15. |
| Liczba poziomów | liczba całkowita | Właściwość ta definiuje liczby poziomów, które powinny być pokazywane, jeśli dla właściwości **Włącz wielopoziomowe menu nawigacji** jest ustawiona wartość **Prawda**. |
| Statyczny element menu| Tablica wartości| Statyczne elementy menu, które kojarzą nazwę elementu menu z łączem do statycznej strony witryny. Można utworzyć elementy menu poniżej innych elementów menu. Domyślnie menu statyczne pojawia się na poziomie głównym i zostanie dołączone do hierarchii nawigacji kanału, jeśli taka istnieje. |
| Pokazywanie menu głównego | **Prawda** lub **Fałsz** | Gdy ta właściwość jest włączona, menu nawigacji można zdefiniować za pomocą niestandardowego katalogu głównego (na przykład **Kup teraz**). Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.15. |
| Menu główne | ciąg | Ta właściwość może służyć do definiowania tekstu dla niestandardowego katalogu głównego, jeśli właściwość **Pokazywanie menu głównego** ma wartość **Prawda**. |

Na poniższej ilustracji pokazano przykład obrazu kategorii wyświetlanego w menu nawigacji witryny Fabrikam.
![Przykład modułu menu nawigacji z obrazami kategorii](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Dodawanie modułu menu nawigacji do modułu nagłówka

Aby uzyskać szczegółowe informacje na temat dodawania modułu menu nawigacji do modułu nagłówka, skorzystaj z [modułu nagłówka](author-header-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł szlaków nawigacyjnych](add-breadcrumb.md)

[Moduł wyboru witryny](site-selector.md)

[Moduł pola zakupu](add-buy-box.md)

[Zgodność z plikami cookie](cookie-compliance.md)

[Moduł nagłówka](author-header-module.md)

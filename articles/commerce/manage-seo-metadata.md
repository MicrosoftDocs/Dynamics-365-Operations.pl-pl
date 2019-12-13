---
title: Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania
description: W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b69d9d2769023967e2b94fef1b8fcf6b5b3357c5
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698356"
---
# <a name="manage-seo-metadata"></a>Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Metadane funkcji optymalizacji wyszukiwania dla witryny można zarządzać za pomocą map witryn i metadanych strony.
    
## <a name="site-maps"></a>Mapy witryny

Mapa witryny to lista stron witryny w formacie XML, która jest czytelna dla maszyn. Jest ona przeznaczona do używania przez silniki wyszukiwania, dzięki czemu mogą one zapewnić lepsze wyniki wyszukiwania w witrynie. Mapy witryn mogą być ręcznie wprowadzane do silników wyszukiwania lub publikowane w pliku robots.txt.

Dynamics 365 Commerce obsługuje automatyczne generowanie map witryn. Mapy witryn są automatycznie aktualizowane podczas publikowania i cofnięcia publikowania stron.

### <a name="turn-on-site-map-generation"></a>Włącz generowanie mapy witryny

1. Zaloguj się do narzędzia autorskiego.
1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.
1. Upewnij się, że opcja **Mapy witryny włączone** jest włączona

## <a name="page-metadata"></a>Metadane strony

Dynamics 365 Commerce umożliwia zarządzanie metadanymi funkcji optymalizacji dla poszczególnych stron. Informacje te można wyświetlać i modyfikować w sekcji **Właściwości adresu SEO** w kontenerze stron. Obecnie obsługiwane są następujące właściwości metadanych SEO:

- Nazwa
- Opis
- słowa kluczowe SEO
- etykiety aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modyfikuj metadane strony

Aby skonfigurować metadane strony, wykonaj następujące kroki.

1. W obszarze **Witryny** wybierz firmę **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie wybierz **Strony**.
1. Wybierz stronę główną, aby otworzyć ją w edytorze stron.
1. W okienku akcji wybierz opcję **Wyewidencjonuj**.
1. W okienku właściwości po prawej stronie rozwiń **Domyślne tagi metadanych**.
1. Aby dodać nowy tag metadanych, wybierz opcję **Dodaj**, a następnie wprowadź znacznik w polu.

    Aby usunąć istniejący tag metadanych, należy wybrać symbol kosza na śmieci.

1. Wybierz **Zapisz** i następnie wybierz **Zaewidencjonuj**.
1. W polu **Komentarze** wprowadź **Zaktualizowane Tagi metadanych**, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)


---
title: Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania
description: W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06d2da60695be499971904451fd56fb8a64dfd64c9192d93f87ababb349e9378
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751574"
---
# <a name="manage-seo-metadata"></a>Zarządzanie metadanymi SEO

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.

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
1. Na pasku poleceń wybierz opcję **Edytuj**.
1. W okienku właściwości po prawej stronie rozwiń **Domyślne tagi metadanych**.
1. Aby dodać nowy tag metadanych, wybierz opcję **Dodaj**, a następnie wprowadź znacznik w polu. Aby usunąć istniejący tag metadanych, należy wybrać symbol kosza na śmieci.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
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

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

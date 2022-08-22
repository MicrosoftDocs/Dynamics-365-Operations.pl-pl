---
title: Zarządzanie metadanymi SEO
description: W tym artykule opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/21/2022
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
ms.openlocfilehash: 4b04d675a903279e667e1f5fcee387f05d979e81
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276836"
---
# <a name="manage-seo-metadata"></a>Zarządzanie metadanymi SEO

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.

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
1. W edytorze stron, na górze kontrolki konspektu strony po lewej stronie, wybierz opcję **Tryb konspektu** (symbol koła zębatego), a następnie wybierz **Zaawansowany widok konspektu**.
1. W widoku konspektu rozwiń kontrolki drzewa, aby pokazać zawartość slotu **HTML head**.
1. W slocie **Nagłówek HTML** wybierz odpowiedni moduł SEO (na przykład **Podsumowanie strony**, **Podsumowanie strony produktu**, **Podsumowanie strony kategorii** lub **Metatagi**).
1. W okienku właściwości po prawej stronie edytuj pożądane dane SEO dla wybranego modułu SEO (na przykład **Tytuł**, **Opis** lub **Udostępnianie obrazka**).
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. W polu **Komentarze** wprowadź **Zaktualizowane dane SEO**, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.

> [!TIP]
> Autorzy mogą używać opcji **Tryb konspektu** (symbol koła zębatego) u góry lewej kontrolki konspektu w edytorze stron, aby przełączać się między **Podstawowym widokiem konspektu** a **Zaawansowanym widokiem konspektu**. **Podstawowy widok konspektu** jest ustawieniem domyślnym i filtruje konspekt tak, że pokazuje tylko moduły w slocie HTML **Tekst główny** dla danej strony. **Zaawansowany widok konspektu** pokazuje cały moduł strony, włączając w to **Nagłówek HTML**, **początek tekstu** i **koniec tekstu**. Ten widok jest przydatny, gdy autorzy muszą edytować specyficzne ustawienia SEO lub modułu skryptu dla danej strony.

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

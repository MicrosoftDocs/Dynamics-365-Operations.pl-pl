---
title: Moduł listy obrazów
description: W tym artykule opisano moduły listy obrazów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: e89624a98d3cbdd861391e994386ae57d2c38aa0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269843"
---
# <a name="image-list-module"></a>Moduł listy obrazów

[!include [banner](includes/banner.md)]

W tym artykule opisano moduły listy obrazów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł listy obrazów może być używany do łatwego dodawania kolekcji (tablicy) obrazów do stron witryny. Każdy obraz w tablicy można skonfigurować za pomocą tekstu akapitowego i adresów URL łączy. Moduł listy obrazów najlepiej nadaje się do wyświetlania logo marek lub listy zawierającej logo.

> [!IMPORTANT]
> - Moduł listy obrazów jest dostępny w bibliotece modułów Commerce od wydania Dynamics 365 Commerce w wersji 10.0.20.
> - Moduł listy obrazów jest prezentowany w temacie Adventure Works.

Na poniższej ilustracji przedstawiono przykład, w którym moduł listy obrazów wyświetla listę tekstu zawierającego logo na stronie witryny Business-to-Consumer (B2C) firmy Adventure Works.

![Przykład modułu listy obrazów, który wyświetla listę tekstów zawierających logo](./media/Image_list.PNG)

Na poniższej ilustracji przedstawiono przykład, w którym moduł listy obrazów wyświetla logo marki na stronie witryny Business-to-Business (B2B) firmy Adventure Works.

![Przykład modułu listy obrazów, w którym są wyświetlane logo marki](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Właściwości modułu listy obrazów

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Nagłówek tekstowy modułu listy obrazów. |
| Lista obrazów    | Obrazy, tekst i adresy URL | Każdy element tablicy to obraz, któremu towarzyszy tekst akapitu i adres URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Dodawanie modułu listy obrazów do nowej strony

Aby dodać moduł listy obrazów do nowej strony i ustawić wymagane właściwości w kreatorze stron Commerce, wykonaj poniższe kroki.

1. Przejdź do formularza **Szablony** i otwórz szablon marketingowy dla strony głównej witryny (lub utwórz nowy szablon marketingowy).
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Lista obrazów** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do formularza **Strony** i otwórz stronę główną witryny (lub utwórz nową stronę główną, używając szablonu marketingowego).
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Lista obrazów** i wybierz przycisk **OK**.
1. W okienku właściwości modułu listy obrazów dodaj nagłówek (na przykład **Nasze marki**).
1. Dodaj element listy obrazów i określ obraz, tekst akapitu oraz adres URL przekierowania.
1. Dodaj element listy obrazów i określ obraz, tekst tekstu oraz adres URL przekierowania.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Motyw Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

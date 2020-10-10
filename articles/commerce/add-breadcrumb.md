---
title: Moduł nawigacyjny
description: W tym temacie opisano moduły nawigacyjne i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7c6f215c3a7539cc16b0d72594702e6bdde7c58e
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817117"
---
# <a name="breadcrumb-module"></a>Moduł nawigacyjny

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły nawigacyjne i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduły do stron nadrzędnych służą do tworzenia pomocniczej nawigacji na stronach witryny. Zazwyczaj są one wyświetlane u góry strony, pod nagłówkiem. Chociaż moduły stron nadrzędnych można dodawać do dowolnej strony, są one najczęściej używane na stronach szczegółów produktów (PDPs), do wyświetlania hierarchii kategorii produktów oraz szybkiego sposobu poruszania się po witrynie. Za pomocą modułu łączy wielokrotnych można również wyświetlić łącze „Powrót do wyników”, gdy użytkownicy otworzą PDP na stronie wyszukiwania lub listy. Dzięki temu użytkownicy mogą szybko powrócić do strony przefiltrowanej listy, aby kontynuować zakupy.

Na stronach z kontekstem kategorii produktów, takimi jak PDPs i strony kategorii, moduły do stron nadrzędnych pokazują hierarchię kategorii. Na stronach, które nie mają kontekstu kategorii, moduły nawigacyjne pokazują domyślnie **&lt;Katalog główny witryny&gt; / &lt;Obecna strona&gt;**. Moduły nawigacyjne można również skonfigurować ręcznie na innych typach stron witryny w celu wyświetlania łączy do konkretnych stron w witrynie.

> [!NOTE]
> Moduł łącza do stron nadrzędnych jest dostępny w wydaniu Dynamics 365 Commerce 10.0.12.

Poniższy obraz przedstawia przykład modułu nawigacyjnego, który pokazuje hierarchię kategorii dla PDP.

![Przykład modułu nawigacyjnego](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Ustawienia modułu nawigacyjnego

Moduł łącza do stron nadrzędnych opiera się na ustawieniu **Typ widoku nawigacyjnego w PDP**, które jest zdefiniowane **Ustawienia witryny \> Rozszerzenia** w w konstruktorze witryn. Tao ustawienie ma trzy możliwe wartości:

- **Wyświetl hierarchię kategorii** — gdy ta wartość jest zaznaczona, w module nawigacyjnym zostanie wyświetlona pełna hierarchia kategorii produktu wyświetlanego na formularzu PDP.
- **Powrót do wyników** — po wybraniu tej wartości w module nawigacyjnym zostanie wyświetlone łącze „Powrót do wyników” na karcie PDP, jeśli użytkownik otworzy moduł PDP w module umożliwiającym wykonanie łącza „Powrót do wyników”. Ta funkcja jest dostępna, gdy użytkownik nawiguje od stron kategorii, wyszukiwania, listy i rekomendacji. Aby można było obsługiwać tę funkcję, moduły zbierania produktów i wyników wyszukiwania mają właściwość o nazwie **Zezwalaj na powrót do wyników na PDP**. Ta właściwość umożliwia określenie, które moduły powinny obsługiwać łącza „Powrót do wyników” dla zestawu PDP. Na przykład po wybraniu opcji **Powróć do wyników** w ustawieniu **Typ widoku nawigacyjnego w PDP** modułu nawigacyjnego i wybranie **Zezwalaj na powrót do wyników na PDP** dla modułu wyników wyszukiwania stron wyszukiwania, łącze „Powrót do wyników” będzie wyświetlane, gdy użytkownicy przejdą ze strony wyszukiwania do PDP.
- **Wyświetl hierarchię kategorii i wróć do wyników** — Ta wartość jest kombinacją dwóch poprzednich wartości. Po wybraniu tej wartości w module nawigacyjnym będzie widoczna zarówno pełna hierarchia kategorii, jak i łącze „Powrót do wyników” (jeśli zostało skonfigurowane) na PDP.

> [!IMPORTANT]
> Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.12. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="breadcrumb-module-properties"></a>Właściwości modułu nawigacyjnego

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Folder główny | Tekst lub łącze| Ta właściwość opcjonalna określa tekst łącza oraz cel łącza dla katalogu głównego witryny sieci Web. Jeśli ta właściwość nie jest skonfigurowana, nie zostanie zdefiniowany żaden katalog główny. |
| Łącze nawigacyjne | Łącze | Ta właściwość opcjonalna określa łącza do ręcznie skonfigurowanych łączy nawigacyjnych, jeśli te łącza są wymagane. Łącza są wyświetlane w kolejności, w jakiej są wyświetlane. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Dodawanie modułu nawigacyjnego do nowej strony

Aby dodać moduł nawigacyjnego do PDP i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny /> Rozszerzeń**, a następnie dla ustawienia **Typ widoku nawigacyjnego w PDP** wybierz **Wyświetl hierarchię kategorii**.
1. Przejdź do **Szablony** i wybierz szablon PDP.
1. W gnieździe **Kontener**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Stron** i otwórz element PDP, w którym jest używany szablon PDP. Jeśli PDP jeszcze nie istnieje, utwórz go.
1. W gnieździe **Kontener**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.
1. W okienku właściwości gniazda **Nawigacyjne** w obszarze **Element główny** wybierz opcję **Tekst łącza**.
1. W oknie dialogowym **Tekst łącza** wprowadź tekst **Strona główna**, a następnie w obszarze **Cel łącza** wybierz opcję **Dodaj łącze**.
1. W oknie dialogowym **Dodaj łącze** wybierz łącze do źródła nawigacyjnego, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Moduły kolekcji produktów](product-collection-module-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)

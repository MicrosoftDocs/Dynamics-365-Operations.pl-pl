---
title: Modyfikacja istniejącej strony witryny
description: W tym temacie opisano sposób modyfikowania istniejącej strony witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 47a7d17b97631ba469a9b68f5f6cf492ebccde6f
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097313"
---
# <a name="modify-an-existing-site-page"></a>Modyfikacja istniejącej strony witryny


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób modyfikowania istniejącej strony witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

W przypadku konieczności zmodyfikowania strony pierwszym krokiem jest otwarcie jej w edytorze stron. Przejdź do witryny, która zawiera stronę, a następnie na liście stron znajdź żądaną stronę. Jeśli nie możesz znaleźć strony, możesz skorzystać z funkcji wyszukiwania rozszerzonego narzędzia autorskiego. Należy wpisać dokładną nazwę strony lub wpisać kilka pierwszych liter, a następnie gwiazdkę (\*). Zostanie wyświetlona filtrowana lista stron. Tej listy można użyć, aby znaleźć żądaną stronę. Po znalezieniu poprawnej strony wybierz nazwę strony, aby otworzyć stronę w edytorze stron.

> [!TIP]
> Jeśli strona jest widoczna w Inspektorze stron, można wybrać **Edytuj** i wyewidencjonować stroę przed otwarciem jej w edytorze stron. W ten sposób można wyewidencjonować wiele stron jednocześnie.

Po otwarciu strony w edytorze stron należy upewnić się, że została ona wyewidencjonowana dla tego użytkownika. Pasek poleceń w narzędziu autorskim jest dynamiczny, kontekstowy i z uwzględnieniem stanu. W związku z tym są wyświetlane tylko akcje, które można obecnie wykonać na stronie. Jeśli na przykład strona nie jest wyewidencjonowana dla użytkownika, przyciski **Zapisz** i **Zakończ edycję** nie są wyświetlane na pasku poleceń. Stan strony jest również pokazany po prawej stronie okna.

Jeśli strona nie jest jeszcze wyewidencjonowana dla użytkownika, wybierz opcję **Edytuj** na pasku poleceń. Pasek poleceń zmieni się, odzwierciedlając nowy stan strony. Użytkownik otrzymuje również powiadomienie informujące o tym, że strona została wyewidencjonowana dla danego użytkownika.

Następnym krokiem jest wprowadzenie rzeczywistych zmian. Często używasz drzewa konspektu strony po lewej stronie, aby znaleźć i wybrać moduł, który chcesz zmienić, a następnie wprowadzić zmiany w panelu właściwości po prawej stronie. 

Jednak ta zmiana może czasami wymagać dodania lub usunięcia modeli lub fragmentów. Aby dodać fragment lub moduł, należy użyć drzewa konspektu strony, aby znaleźć gniazdo, do którego ma zostać dodany moduł lub fragment, a następnie wybrać przycisk wielokropka (**...**) dla tego gniazda. Zostanie wyświetlone menu zawierające polecenia służące do dodawania modułu lub fragmentu. Aby usunąć moduł lub fragment, znajdź go i zaznacz w drzewie konspektu strony, wybierz przycisk wielokropeka, a następnie wybierz polecenie usunięcia modułu lub fragmentu.

> [!TIP]
> Można również wyświetlać i edytować właściwości każdego modułu widocznego w wizualnym konstruktorze witryn, zaznaczając go bezpośrednio.

Po wprowadzeniu zmian i przejrzeniu ich efektu należy zaewidencjonować stronę, wybierając opcję **Zakończ edycję** na pasku poleceń. 

Aby natychmiast opublikować zmiany, wybierz opcję **Opublikuj** na pasku poleceń. Najnowsza zaewidencjonowana wersja zmodyfikowanej strony została opublikowana i stanie się dostępna dla użytkowników zewnętrznych, którzy przeglądają witrynę. 

## <a name="example-change-the-video-on-the-home-page"></a>Przykład: zmiana obrazu wideo na stronie głównej

Poniższy przykład ilustruje sposób modyfikowania strony głównej przez zmianę wideo wyświetlanego w module odtwarzacza wideo.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie wybierz **Strony**.
1. Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.
1. Na pasku poleceń wybierz opcję **Edytuj**.
1. W konspekcie strony wybierz **Główne** gniazdo.
1. W obszarze **Głównym** gniazda rozwiń wszystkie moduły kontenera cieczy.
1. Znajdź i wybierz moduł odtwarzacza wideo.
1. W panelu właściwości po prawej wybierz właściwość **wideo**. Zostanie wyświetlony selektor środków trwałych.
1. W obszarze wyboru składników majątku wybierz dostępny zasób wideo lub wybierz opcję **Przekaż nowy składnik**, aby przekazać nowy składnik wideo.
1. Kliknij przycisk **OK**.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. W polu **Komentarze** wprowadź **Zmieniono wideo**, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd aktualizowanej strony produktu. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
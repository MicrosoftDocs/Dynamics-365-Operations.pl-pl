---
title: Zapisywanie, pogląd i publikowanie strony
description: W tym temacie opisano, jak zapisać, wyświetlić podgląd i opublikować stronę w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 04200264fabca265484b5e66426810efe8028a50
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002827"
---
# <a name="save-preview-and-publish-a-page"></a>Zapisywanie, pogląd i publikowanie strony


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak zapisać, wyświetlić podgląd i opublikować stronę w Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Zapisywanie strony

Aby zapisać stronę, należy ją wyewidencjonować i otworzyć w edytorze stron. Stronę należy zapisać bezpośrednio po jej zmodyfikowaniu, aby zagwarantować przechowywanie wprowadzonych zmian.

Po zapisaniu strony zmiany są widoczne tylko dla użytkownika. Operacja zapisywania jest przeznaczona głównie do przechowywania zmian, gdy strona nie jest jeszcze gotowa do zaewidencjonowania. Po zakończeniu modyfikowania strony zaleca się zaewidencjonowanie jej w systemie, aby zmiany stały się widoczne dla innych osób. Na tym etapie strona może być również wyewidencjonowana przez innych użytkowników, którzy muszą ją zmodyfikować.

## <a name="preview-a-page"></a>Podgląd strony

Narzędzie autorskie Tool oferuje dwa rodzaje funkcji wersji podglądu: „wyświetlane informacje to okienko podglądu” (WYSIWYG) w edytorze stron i osobnym oknie podglądu.

Gdy jest używany edytor stron, w środkowym okienku jest wyświetlany komunikat „widoczny dla użytkownika” (WYSIWYG). Podgląd ten jest automatycznie aktualizowany przy każdym zapisywaniu strony. Można je również zaktualizować ręcznie, klikając przycisk **Odśwież** na pasku poleceń. Podgląd w trybie WYSIWYG renderuje stronę w taki sposób, jak będzie widoczna dla użytkowników witryny.

Po zakończeniu modyfikowania strony można wyświetlić jej podgląd, aby zobaczyć, co będą widoczne dla klientów. Aby wyświetlić podgląd strony, należy wybrać opcję **Podgląd** na pasku poleceń. Podgląd zostanie wyświetlony w osobnym oknie przeglądarki. Strona w oknie podglądu jest renderowana w taki sposób, jak będzie widoczna dla użytkownika witryny. Można zmienić rozmiar okna, aby upewnić się, że moduły odpowiadające są poprawnie renderowane we wszystkich portach widoków.

> [!NOTE]
> Do wyświetlenia podglądu nieopublikowanej zawartości jest wymagane uwierzytelnianie i poprawne uprawnienia. Dlatego jeśli adres URL podglądu zostanie udostępniony innej osobie, musi mieć odpowiednie uprawnienia, aby uzyskać dostęp do tej zawartości.

## <a name="publish-a-page"></a>Opublikuj stronę

Gdy strona jest gotowa, następnym krokiem jest jej opublikowanie, dzięki czemu użytkownicy zewnętrzni będą mogli wyświetlić zawartość. Zanim będzie możliwe opublikowanie strony, musisz ją zaewidencjonować.

Strony można publikować i cofać ich publikowanie za pomocą Inspektora stron lub edytora stron. W Inspektorze stron jest wyświetlana lista stron umożliwiająca wykonywanie operacji zbiorczych. Edytora stron można używać do publikowania lub cofania publikowania tylko jednej strony otwartej w tym edytorze.

Aby opublikować co najmniej jedną stronę za pomocą Inspektora stron, zaznacz strony, upewnij się, że są one zaewidencjonowane, a następnie wybierz opcję **Opublikuj** na pasku poleceń. Strony zostaną opublikowane, a użytkownik otrzymuje powiadomienie o operacji w narzędziu autorskim.

Aby opublikować pojedynczą stronę z edytora stron, procedura jest podobna. Gdy strona jest otwarta w edytorze stron, upewnij się, że została zaewidencjonowana w systemie, a następnie wybierz opcję **Opublikuj** na pasku poleceń. Strona zostanie opublikowana, a użytkownik otrzymuje powiadomienie o operacji.

Po opublikowaniu strony publikowana jest tylko zawartość strony. Użytkownik i inni użytkownicy mogą przejść do tej strony i wyświetlić ją tylko po powiązaniu z nim adresu URL. Adres URL musi być publikowany oddzielnie.

> [!IMPORTANT]
> Zanim będzie możliwe opublikowanie strony, wszelkie obrazy lub fragmenty, do których odwołuje się Strona, muszą być już opublikowane.

## <a name="save-preview-and-publish-a-home-page"></a>Zapisywanie, pogląd i publikowanie strony głównej

Aby zapisać, przejrzeć i opublikować stronę główną, należy wykonać następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie wybierz **Strony**.
1. Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.
1. Wybierz **Wyewidencjonuj**.
1. Zmodyfikuj stronę stosownie do potrzeb.
1. Wybierz **Zapisz** i następnie wybierz **Zaewidencjonuj**.
1. W polu **Komentarze** wprowadź notatkę dotyczącą wprowadzonych zmian, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.

## <a name="publish-a-url"></a>Publikuj adres URL

Aby opublikować adres URL, należy wykonać następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie zaznacz **adresy URL**.
1. Znajdź i zaznacz adres URL, który chcesz opublikować.
1. Na pasku poleceń wybierz opcję **Opublikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania](manage-seo-metadata.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

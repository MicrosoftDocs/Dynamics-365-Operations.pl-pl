---
title: Moduł harmonijki
description: W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: ba973299291276fe48d82360e203ca28f02aaffb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796277"
---
# <a name="accordion-module"></a>Moduł typu accordion

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły harmonijki i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły harmonijki to moduły podobne do kontenerów, które służą do organizowania informacji lub modułów na stronie, zapewniając składaną funkcję szuflady. Na dowolnej stronie można używać modułu harmonijki.

W każdym module harmonijki można dodać jeden lub więcej modułów pozycji harmonijki. Każdy moduł pozycji harmonijki reprezentuje szufladę zwijaną. W każdym module pozycji harmonijki można dodać jeden lub więcej modułów. Nie ma ograniczeń dotyczących typów modułów, które można dodać do modułu pozycji harmonijki.

Poniższy obraz przedstawia przykład modułu harmonijki, który jest używany do organizowania informacji na stronie często zadawanych pytań dotyczących sklepu.

![Przykład modułu harmonijki](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Właściwości modułu harmonijki

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek | Tekst | Właściwość ta określa opcjonalny nagłówek tekstowy dla modułu harmonijki. |
| Rozwiń wszystko | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, funkcja Rozwiń/Zwiń jest włączona, co umożliwia rozwijanie i zwijanie wszystkich towarów w module harmonijki. |
| Styl interakcji | **Niezależne** lub **Rozwijaj tylko jeden element** | Ta właściwość definiuje styl interakcji dla pozycji. Jeśli wartość jest ustawiona jako **Niezależne**, każdy z nich może być rozwinięty lub zwijany niezależnie. Jeśli wartość jest ustawiona na **Rozwijaj tylko jeden element**, w danym momencie może być rozwinięty tylko jeden towar. Po rozwinięciu towarów poprzednio rozwinięte elementy są zwijane. |

## <a name="accordion-item-module-properties"></a>Właściwości modułu pozycji harmonijki

| Nazwa właściwości | Wartości | opis |
|----------------|--------|-------------|
| Nazwa | Tekst | Ta właściwość określa tekst tytułu dla modułu pozycji harmonijki. Wybierając region tytułu, użytkownicy będą mogli rozwijać lub zwijać sekcje. |
| Rozwiń domyślnie | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, podczas wczytywania strony domyślnie jest rozwinięta pozycja harmonijki. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Dodawanie modułu harmonijki do strony Często zadawanych pytań

Aby dodać moduł harmonijki do strony Często zadawanych pytań i ustawić wymagane właściwości w konstruktorze witryn, wykonaj następujące kroki.

1. Przejdź do **Strony** i użyj szablonu marketingowego Fabrikam (lub dowolnego szablonu, który nie ma ograniczeń), aby utworzyć nową stronę o nazwie **Często zadawane pytania o sklepie**.
1. W gnieździe **Głównym** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Harmonijka** i wybierz przycisk **OK**.
1. W okienku właściwości modułu harmonijki wybierz pozycję **Nagłówek** obok symbolu ołówka.
1. W oknie dialogowym **Nagłówek**, w obszarze **Tekst nagłówka** wprowadź **Często zadawane pytania**. Następnie wybierz opcję **OK**.
1. W okienku właściwości modułu harmonijka zaznacz pole wyboru **Pokaż wszystkie rozwinięte**, a następnie w polu **Styl interakcji** wybierz opcję **Niezależne**.
1. W gnieździe **Harmonijka** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element harmonijki** i wybierz przycisk **OK**.
1. W okienku właściwości modułu pozycji harmonijki w obszarze **Tytuł** wprowadź tekst tytułu (np. **Jak działają zwroty?**).
1. W gnieździe **Pozycja harmonijki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**.
1. W okienku właściwości modułu blok tekstu wprowadź akapit tekstu (na przykład **Zwroty muszą być przetwarzane za pośrednictwem biura obsługi. Numer kontaktowy 1-800-FABRIKAM w sprawie zwrotów. Produkty mają 30-dniowe zasady dotyczące zwrotów. Zwroty muszą być inicjowane w tym przedziale czasu.**).
1. W gnieździe **Harmonijka** dodaj kilka więcej modułów. W każdym module pozycji harmonijki należy dodać moduł bloku tekstu z zawartością.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Na stronie zostanie wyświetlony moduł harmonijki z dodaną zawartością.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł tabularny](add-tab.md)

[Moduł bloku tekstu](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
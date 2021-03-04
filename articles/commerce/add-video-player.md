---
title: Moduł odtwarzacza wideo
description: W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3cf7ead9a5340d5db37a87bdf131ba87681d5a82
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414896"
---
# <a name="video-player-module"></a>Moduł odtwarzacza wideo


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł odtwarzacza wideo służy do obsługi odtwarzania wideo. Można go dodać do dowolnej strony, pod warunkiem, że zawartość wideo jest przekazywana do systemu zarządzania zawartością (CMS) i dostępna w nim. Moduł odtwarzacz wideo obsługuje typ multimediów MP4.

## <a name="video-player-module"></a>Moduł odtwarzacza wideo

Moduł odtwarzacz wideo może służyć do prezentowania filmów wideo w witrynie e-Commerce. Obsługuje on wszystkie możliwości odtwarzania, takie jak odtwarzanie, wstrzymywanie, tryb pełnego rozmiaru, opisy audio i napisy kodowane. Moduł odtwarzacz wideo obsługuje również dostosowywanie napisów kodowanych w celu spełnienia standardów dotyczących ułatwień dostępu firmy Microsoft. Można na przykład dostosować rozmiar czcionki i kolor tła.

Moduł odtwarzacza wideo obsługuje również pomocnicze ścieżki audio. Po przekazaniu filmu wideo do CMS można również przesłać pomocniczą ścieżkę audio. Moduł odtwarzacza wideo może następnie odtwarzać pomocniczą ścieżkę audio, jeśli użytkownik ją wybierze.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Przykładowe moduły odtwarzacza wideo w e-Commerce

- Instruktażowe filmy wideo na stronach szczegółów produktu lub na stronach marketingowych
- Promocyjne filmy wideo i materiały wideo informacje o zasadach na dowolnej stronie marketingowej
- Marketingowe pliki wideo, które wyróżniają funkcje produktu na stronach szczegółów produktu lub na stronach marketingowych

Poniższy obraz pokazuje przykład modułu odtwarzacza wideo na stronie głównej.

![Przykład modułu odtwarzacza wideo](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Właściwości modułu odtwarzacza wideo

| Nazwa właściwości         | Wartość                               | opis |
|-----------------------|-------------------------------------|-------------|
| Automatyczne odtwarzanie             | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest automatycznie odtwarzane. |
| Wycisz                  | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, audio jest wyciszane. Domyślną wartością tego odtwarzacza jest **fałsz**. W przeglądarce Chrome klipy wideo autoodtwarzania są domyślnie wyciszone, a dźwięk jest odtwarzany tylko wtedy, gdy użytkownik ręcznie odtworzy wideo. |
| Pętla                  | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, wideo jest zapętlone. |
| Multimedia                 | Ścieżka pliku wideo i nazwa. | Plik wideo odtwarzany w odtwarzaczu wideo. |
| Tryb pełnoekranowy       | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest odtwarzane na pełnym ekranie. |
| Odtwórz wyzwalacz wstrzymania    | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, w pliku wideo jest wyświetlany przycisk Odtwórz/Wstrzymaj. |
| Kontrolki odtwarzacza wideo | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, wyświetlane są kontrolki odtwarzacza wideo. Te formanty obejmują przyciski odtwarzania i wstrzymywania, wskaźnik postępu oraz opcje napisów kodowanych. |
| Ukryj kadr     | **Prawda** lub **Fałsz**               | Film wideo może mieć ramkę plakatu. Jeśli dla wartości tej właściwości jest ustawiona wartość **prawda**, ramka plakatu jest ukryta. |
| Poziom maski            | Liczba z zakresu od **0** do **100** | Maska zastosowana do obrazu wideo dla stylów. |

## <a name="add-a-video-player-module-to-a-page"></a>Dodawanie modułu odtwarzacza wideo na stronie

> [!NOTE] 
> Przed utworzeniem modułu odtwarzacza wideo należy najpierw przekazać wideo do biblioteki multimediów.

Aby dodać moduł odtwarzacza wideo do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon odtwarzacza wideo**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Odtwarzacz wideo** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon odtwarzacza wideo. W sekcji **Nazwa strony** przejdź do **Strona odtwarzacza wideo**, a następnie wybierz przycisk **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Odtwarzacz wideo** i wybierz przycisk **OK**.
1. W okienku właściwości modułu odtwarzacza wideo wybierz opcję **Dodaj klip wideo**.
1. W oknie dialogowym **Selektor elementów multimedialnych** wybierz plik wideo, a następnie wybierz opcję **Przekaż nowy element multimedialny**.
1. W Eksploratorze plików wybierz plik wideo, a następnie wybierz opcję **Otwórz**.
1. W oknie dialogowym **Przekaż element multimedialny** wprowadź odpowiednio tytuł i inne informacje, a następnie kliknij przycisk **OK**.
1. W oknie dialogowym **Selektor elementów multimedialnych** wybierz opcję **Zamknij**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Na stronie powinny być widoczny moduł wideo. Można zmienić dodatkowe ustawienia, aby dostosować zachowanie modułu.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł transparentu promocyjnego](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku tekstu](add-content-rich-block.md)

[Moduł bloku zawartości](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
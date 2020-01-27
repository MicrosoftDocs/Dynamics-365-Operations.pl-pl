---
title: Moduł odtwarzacza wideo
description: W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/02/2019
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
ms.openlocfilehash: 1c78583f39dbacdc7b38e89c33e67ae23731bf8a
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885908"
---
# <a name="video-player-module"></a>Moduł odtwarzacza wideo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły odtwarzacza wideo i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduły odtwarzacza wideo służą do obsługi odtwarzania wideo. Dostępne są dwa moduły odtwarzacza wideo w zestawie Store Starter Kit: moduł odtwarzacz wideo otoczenia i moduł odtwarzacza wideo. Oba odtwarzacze obsługują typ multimediów MP4.

## <a name="ambient-video-player-module"></a>Moduł odtwarzacza wideo otoczenia

Moduł odtwarzacze wideo w otoczeniu obsługuje krótkie wideo informacyjne. Należy go używać w przypadku plików wideo o długości krótszej niż pięć sekund. Ten odtwarzacz obsługuje ograniczone możliwości odtwarzania wideo, takie jak odtwarzanie i wstrzymywanie.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Przykładowe moduły odtwarzacza wideo w otoczeniu w e-Commerce

- Krótkie filmy informacyjne, które wyróżniają nowe produkty na stronie głównej
- Krótkie Filmy informacyjne, które wyróżniają funkcje produktu na stronie szczegółów produktu

### <a name="ambient-video-player-module-properties"></a>Właściwości modułu odtwarzacza wideo otoczenia

| Nazwa właściwości     | Wartość                 | Opis |
|-------------------|-----------------------|-------------|
| Autoodtwarzanie          | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest automatycznie odtwarzane. |
| Wycisz              | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, audio jest wyciszane. Domyślną wartością tego odtwarzacza jest **prawda**. W przeglądarce Google Chrome klipy wideo autoodtwarzania są domyślnie wyciszone, a dźwięk jest odtwarzany tylko wtedy, gdy użytkownik ręcznie odtworzy wideo. |
| Pętla              | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, wideo jest zapętlone. |
| Multimedia             |  Ścieżka pliku wideo i nazwa. | Plik wideo odtwarzany przez odtwarzacz wideo. |
| Elementy sterujące odtwarzania | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, w pliku wideo jest wyświetlany przycisk Odtwórz/Wstrzymaj. Jeśli wartość jest ustawiona na **fałsz**, przycisk Odtwórz/Wstrzymaj nie jest widoczny, ale użytkownicy nadal będą mogli wstrzymywać i wznawiać odtwarzanie wideo za pomocą klawiatury. |

## <a name="video-player-module"></a>Moduł odtwarzacza wideo

Moduł odtwarzacz wideo może służyć do prezentowania filmów wideo w witrynie e-Commerce. Obsługuje on wszystkie możliwości odtwarzania, takie jak odtwarzanie, wstrzymywanie, tryb pełnego rozmiaru i napisy kodowane. Moduł odtwarzacz wideo obsługuje również dostosowywanie napisów kodowanych w celu spełnienia standardów dotyczących ułatwień dostępu firmy Microsoft. Można na przykład dostosować rozmiar czcionki i kolor tła.

Moduł odtwarzacza wideo obsługuje również pomocnicze ścieżki audio. Po przekazaniu filmu wideo można również przesłać pomocniczą ścieżkę audio. Moduł odtwarzacza wideo może następnie odtwarzać pomocniczą ścieżkę audio, jeśli użytkownik ją wybierze.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Przykładowe moduły odtwarzacza wideo w e-Commerce

- Instruktażowe filmy wideo na stronach szczegółów produktu lub na stronach marketingowych
- Promocyjne filmy wideo i materiały wideo informacje o zasadach na dowolnej stronie marketingowej
- Marketingowe pliki wideo, które wyróżniają funkcje produktu na stronach szczegółów produktu lub na stronach marketingowych

### <a name="video-player-module-properties"></a>Właściwości modułu odtwarzacza wideo

| Nazwa właściwości         | Wartość                               | Opis |
|-----------------------|-------------------------------------|-------------|
| Automatyczne odtwarzanie             | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest automatycznie odtwarzane. |
| Wycisz                  | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, audio jest wyciszane. Domyślną wartością tego odtwarzacza jest **fałsz**. W przeglądarce Chrome klipy wideo autoodtwarzania są domyślnie wyciszone, a dźwięk jest odtwarzany tylko wtedy, gdy użytkownik ręcznie odtworzy wideo. |
| Pętla                  | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, wideo jest zapętlone. |
| Multimedia                 | Ścieżka pliku wideo i nazwa. | Plik wideo odtwarzany w odtwarzaczu wideo. |
| Elementy sterujące odtwarzania     | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, w pliku wideo jest wyświetlany przycisk Odtwórz/Wstrzymaj. Jeśli wartość jest ustawiona na **fałsz**, przycisk Odtwórz/Wstrzymaj nie jest widoczny, ale użytkownicy nadal będą mogli wstrzymywać i wznawiać odtwarzanie wideo za pomocą klawiatury. |
| Tryb pełnoekranowy       | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, odtwarzanie wideo jest odtwarzane na pełnym ekranie. |
| Kontrolki              | **Prawda** lub **Fałsz**               | Jeśli wartość jest ustawiona na **prawda**, wyświetlane są wszystkie formanty. Te formanty obejmują przyciski odtwarzania i wstrzymywania, wskaźnik postępu oraz napisy kodowane. |
| Ukryj ramkę plakatu     | **Prawda** lub **Fałsz**               | Film wideo może mieć ramkę plakatu. Jeśli dla wartości tej właściwości jest ustawiona wartość **prawda**, ramka plakatu jest ukryta. |
| Poziom maski            | Liczba z zakresu od **0** do **100** | Maska zastosowana do obrazu wideo dla stylów. |
| Styl ikony na pełny ekran | **Kwadrat** lub **strzałka**             | Styl ikony pełnego ekranu wyświetlanej w odtwarzaczu wideo. |

## <a name="add-a-video-player-module-to-a-page"></a>Dodawanie modułu odtwarzacza wideo na stronie

Aby dodać moduł odtwarzacza wideo do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon odtwarzacza wideo**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł kontenera.
1. W module kontener Dodaj moduły odtwarzaczy wideo i odtwarzacze wideo w otoczeniu.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu odtwarzacza wideo utwórz stronę o nazwie **strona odtwarzacza wideo**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł odtwarzacza wideo w otoczeniu.
1. W ustawieniach modułu odtwarzacze otoczenia wideo przejdź do **Multimedia** i przekaż plik wideo. W razie konieczności można zmienić funkcje **autoodtwarzania**, **pętlę** i inne właściwości.
1. Zapisz i zobacz podgląd strony.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł odtwarzacza wideo.
1. W ustawieniach modułu odtwarzacze otoczenia wideo przejdź do **Multimedia** i przekaż plik wideo.
1. Zapisz i zobacz podgląd strony. Na stronie powinny być widoczne oba moduły wideo. Można zmienić dodatkowe ustawienia, aby dostosować zachowanie każdego modułu.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł funkcji](add-feature-module.md)

[Moduł bohatera](add-hero-module.md)

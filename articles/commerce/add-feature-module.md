---
title: Moduł funkcji
description: W tym temacie opisano moduły funkcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785313"
---
# <a name="feature-module"></a>Moduł funkcji 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły funkcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł funkcji jest używany do marketingowych produktów lub promocji przy użyciu kombinacji obrazów i tekstu. Na przykład sprzedawca może dodać moduł funkcji do strony Szczegóły produktu, aby wyróżnić funkcje produktu.

Moduł funkcji jest sterowany przez dane z systemu zarządzania zawartością (CMS). Jest to samodzielny moduł, który nie zależy od innych modułów na stronie. Moduł funkcji można umieścić na dowolnej stronie witryny, w której detalista chce dokonać obrotu lub promować coś (na przykład produktów, sprzedaży lub funkcji).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Przykłady modułów funkcji w e-Commerce

Moduł funkcji może być używany na następujących stronach:

- Strona szczegóły produktu, w celu zaprezentowania funkcji produktu
- Strona główna, aby promować produkty
- Strona kategorii w celu wyróżnienia kategorii produktów

## <a name="feature-module-properties"></a>Właściwości modułu funkcji

| Nazwa właściwości     | Wartości | Opis |
|-------------------|--------|-------------|
| Wizerunek             | Plik obrazu | Obraz może służyć do reklamy produktu lub promocji. Obraz można przekazać do galerii obrazów lub można użyć istniejącego obrazu. |
| Nagłówek           | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Każdy moduł funkcji może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Akapit         | Tekst akapitu | Moduły funkcji obsługują tekst akapitu w formacie RTF. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link              | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie** | Moduły funkcji obsługują łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |
| Umiejscowienie obrazu   | **Prawy**, **lewy**, **górny** lub **dolny** | Właściwość ta określa pozycję obrazu w odniesieniu do tekstu. Jeśli na przykład zaznaczona jest opcja po **prawej** stronie, obraz pojawi się po prawej stronie tekstu. |
| Rozmiar kolumny obrazu | Wartość z zakresu od **1** do **12** | Właściwość ta określa wielkość obrazu w odniesieniu do tekstu. Rozmiar jest wyrażony jako liczba kolumn na stronie. Na stronie znajduje się 12 kolumn. Domyślnie obraz i tekst mają równy rozmiar (co sześć kolumn). Jednak rozmiar można skorygować w razie potrzeby. |

## <a name="add-a-feature-module-to-a-new-page"></a>Dodawanie modułu funkcji do nowej strony 

Aby dodać moduł funkcji do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonów**i utwórz szablon strony o nazwie **szablon funkcji**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł funkcji.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu funkcji utwórz stronę o nazwie **strona funkcji**.
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** w obszarze **Wybierz moduły** wybierz moduł funkcji i wybierz przycisk **OK**.
1. W drzewie konspektu po lewej wybierz moduł funkcji.
1. W panelu właściwości po prawej wybierz **Dodaj obraz**. Następnie należy wybrać istniejący obraz lub przekazać nowy obraz.
1. Wybierz **Nagłówek**.
1. W oknie dialogowym **nagłówek** dodaj tekst nagłówka, wybierz poziom nagłówka, a następnie kliknij przycisk **OK**.
1. W obszarze **tekst sformatowany**,dodaj tekst w miarę potrzeb.
1. Wybierz **łącze dodaj akcję**.
1. W oknie dialogowym **łącze akcji** dodaj tekst łącza, adres URL łącza oraz etykietę Aria dla łącza, a następnie kliknij przycisk **OK**.
1. Zapisz stronę i wyświetl podgląd zmian.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł bohatera](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)

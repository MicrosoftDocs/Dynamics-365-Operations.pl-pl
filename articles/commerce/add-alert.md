---
title: Moduł alertów
description: W tym temacie opisano moduły alertów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785359"
---
# <a name="alert-module"></a>Moduł alertów

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły alertów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł alertów służy do wyświetlania wbudowanych komunikatów informacyjnych na stronie. Moduły alertów obsługują wiadomość SMS i łącze. Można ich używać do wyświetlania promocji na poziomie całej witryny wyświetlanych na wszystkich stronach witryny e-Commerce. 

Moduły alertów są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Przykłady modułów alertów w e-Commerce

Moduły alertów mogą być używane w nagłówku witryny w celu pokazania promocji lub komunikatów na poziomie całej witryny. Oto kilka przykładów:

„Roczna wyprzedaż kończy się za 10 dni”

„Zaoszczędź na zakupach do szkoły. Kup teraz.”

## <a name="alert-module-properties"></a>Właściwości modułu alertów

| Nazwa właściwości  | Wartość                              | Opis |
|----------------|------------------------------------|-------------|
| Tekst           | Tekst                               | Komunikat tekstowy wyświetlany w module alertu. |
| Wyrównanie tekstu | **Prawo**, **Lewo** lub **Środek** | Wartość określająca sposób wyrównania tekstu w module alertów. |
| Pomiń alert  | **Prawda** lub **Fałsz**              | Jeśli wartość jest ustawiona na **Prawda**, odbiorca może anulować alert. |
| Link           | Adres URL                                | Adres URL opcjonalnego linku. |

## <a name="add-an-alert-module-to-a-page"></a>Dodawanie modułu alertów do strony 

Aby dodać moduł alertów do strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon alertu**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł alertów.
1. Zaewidencjonuj szablon i opublikuj go. 
1. Za pomocą utworzonego właśnie szblonu alertu utwórz stronę o nazwie **strona alertu**. 
1. W **Głównym** gnieździe na nowej stronie dodaj moduł alertów.
1. W ustawieniach modułu alertów wprowadź tekst alertu. Inne właściwości można edytować, jeśli moduł alertów ma być dostosowany dalej.
1. Zapisz i zobacz podgląd strony. W górnej części strony powinien pojawić się alert z dodanym tekstem.
1. Zaewidencjonuj stronę i opublikuj ją. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł funkcji](add-feature-module.md)

[Moduł bohatera](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)

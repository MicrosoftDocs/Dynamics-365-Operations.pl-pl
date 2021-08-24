---
title: Brakuje produktów i kategorii po skopiowaniu środowiska
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku braku produktów i kategorii po skopiowaniu witryny do jednego środowiska lub w tym samym środowisku.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 813289db052323fd87cd5a65184d71a580f1a3e0df9ea7d50a752e26b3962d1c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763627"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Brakuje produktów i kategorii po skopiowaniu środowiska

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku braku produktów i kategorii po skopiowaniu witryny do jednego środowiska lub w tym samym środowisku.

## <a name="description"></a>opis

Gdy witryna zostanie skopiowana z jednego środowiska do innego lub w tym samym środowisku, w tej samej witrynie brakuje produktów i kategorii. Brak produktów i kategorii z witryny sklepu handlu elektronicznego i karty **Produkty** w Konstruktorze witryn portalu Commerce.

## <a name="resolution"></a>Rozdzielczość

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mapowanie numeru jednostki operacyjnej kanału na nowo skopiowaną witrynę w Konstruktorze witryn Commerce

Aby zmapować numer jednostki operacyjnej kanału (OUN) do nowo skopiowanej witryny w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Wybierz nowo skopiowaną witrynę.
1. W obszarze **Ustawienia witryny** wybierz opcję **kanały**.
1. Obok nazwy kanału wybierz wielokropek (**...**), a następnie wybierz pozycję **Zmień kanał sklepu internetowego**.
1. W oknie dialogowym **Zmiana kanału sklepu internetowego** wybierz kanał do mapowania na nowo skopiowaną witrynę, a następnie wybierz przycisk **OK**.
1. Wybierz **Zapisz i opublikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](../associate-site-online-store.md)

---
title: Omówienie cyklu życia zlecenia produkcyjnego
description: Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80031737ab0d0c4ab1e4dbd5646ad91f1a010cd5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435368"
---
# <a name="production-order-lifecycle-overview"></a>Omówienie cyklu życia zlecenia produkcyjnego

[!include [banner](../includes/banner.md)]

Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.

Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego. Po utworzeniu zlecenie otrzymuje stan **Utworzone**. Po zakończeniu zlecenie otrzymuje stan **Zakończone**. Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku. Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.

Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego. Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji. Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.

Zlecenie produkcyjne można tworzyć w następujących sytuacjach:

-   Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.
-   Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).
-   Tworzenie ręczne.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
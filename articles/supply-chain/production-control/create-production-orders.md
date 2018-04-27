---
title: "Tworzenie zleceń produkcyjnych"
description: "Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d962dbf5a5a4e3847252171d3631f78341640bc7
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="create-production-orders"></a>Tworzenie zleceń produkcyjnych

[!INCLUDE [banner](../includes/banner.md)]

Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.

Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego. Po utworzeniu zlecenie otrzymuje stan **Utworzone**. Po zakończeniu zlecenie otrzymuje stan **Zakończone**. Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku. Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.

Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego. Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji. Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.

Zlecenie produkcyjne można tworzyć w następujących sytuacjach:

-   Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.
-   Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).
-   Tworzenie ręczne.






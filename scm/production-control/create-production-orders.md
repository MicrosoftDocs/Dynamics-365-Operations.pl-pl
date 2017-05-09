---
title: "Tworzenie zleceń produkcyjnych"
description: "Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 33d2e4f1a6bc8bc28e43b4c985d9a780a9481e97
ms.lasthandoff: 03/31/2017


---

# <a name="create-production-orders"></a>Tworzenie zleceń produkcyjnych

[!include[banner](../includes/banner.md)]


Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.

Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego. Po utworzeniu zlecenie otrzymuje stan **Utworzone**. Po zakończeniu zlecenie otrzymuje stan **Zakończone**. Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku. Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.

Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego. Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji. Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.

Zlecenie produkcyjne można tworzyć w następujących sytuacjach:

-   Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.
-   Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).
-   Tworzenie ręczne.






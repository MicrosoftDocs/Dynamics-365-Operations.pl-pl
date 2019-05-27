---
title: Grupowa aktualizacja środków trwałych
description: Jeśli są stosowane księgi, istnieje możliwość zmiany konwencji amortyzacji dla grup środków trwałych będących częścią tej samej księgi.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b740f1fe710c2278bd5ac5f8d615f0e305cd7df1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565376"
---
# <a name="fixed-asset-mass-update"></a>Grupowa aktualizacja środków trwałych

[!include [banner](../includes/banner.md)]

Jeśli są stosowane księgi, istnieje możliwość zmiany konwencji amortyzacji dla grup środków trwałych będących częścią tej samej księgi.

Jeśli na przykład firma znajduje się w Stanach Zjednoczonych i w czwartym kwartale roku wyeksploatowała ponad 40 procent swoich środków trwałych, musi użyć konwencji amortyzacji „w trakcie kwartału”. W celu zmiany wszystkich środków trwałych wymagających zmiany konwencji amortyzacji można użyć procesu aktualizacji grupowej. 

Podczas aktualizowania konwencji amortyzacji dla środków trwałych należy usunąć wszystkie transakcje amortyzacji, które istnieją dla tych środków trwałych. Ponadto należy usunąć wszystkie transakcje korekt amortyzacji, podwyższenia amortyzacji i amortyzacji dodatkowych dla tych środków trwałych. 

Aby zaktualizować konwencję amortyzacji dla środków trwałych, które zostały już zlikwidowane, najpierw trzeba usunąć istniejące transakcje likwidacji. Należy również usunąć wszystkie transakcje, które zostały wygenerowane w wyniku procesu likwidacji. 

Po zaktualizowaniu konwencji amortyzacji dla środków trwałych można przetworzyć amortyzację oraz amortyzację dodatkową dla poszczególnych środków trwałych. Istnieje również możliwość ręcznego tworzenia korekt amortyzacji, jeśli są wymagane zmiany.






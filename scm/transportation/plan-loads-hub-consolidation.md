---
title: "Planowanie ładunków przy użyciu konsolidacji w centrum"
description: "W tym artykule opisano funkcjonalność konsolidowania wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3eb4bc384f2aada2d29e9d296fe7abe61525431f
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="plan-loads-using-hub-consolidation"></a>Planowanie ładunków przy użyciu konsolidacji w centrum

[!include[banner](../includes/banner.md)]


W tym artykule opisano funkcjonalność konsolidowania wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu.

Może być przydatne skonsolidowanie wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu.

## <a name="building-loads"></a>Kompilowanie ładunków
Zanim będzie można używać konsolidacji w centrum, należy włączyć opcję **Planowanie w drodze** na karcie **Parametry zarządzania transportem**. Należy również utworzyć centra, w których będzie następowała konsolidacja. Poniższy diagram przedstawia przykład konsolidacji w centrum. W tym przypadku zamówienia sprzedaży z różnych magazynów trafiają do tego samego odbiorcy. Podstawowe ładunki są tworzone na podstawie zamówień sprzedaży w zwykły sposób, za pomocą strony **Warsztat planowania wysyłki ładunku**. Aby skonsolidować dwa ładunki w centrum, zanim zostaną dostarczone do odbiorcy, na stronie **Warsztat planowania wysyłki ładunku** w polu **Transport** zaznacz opcję **Konsolidacja centrum**. Po wybraniu odpowiedniego centrum dla każdego ładunku ładunki będą miały centrum jako miejsce docelowe „dostawy”. Ponadto istnieją dwa „wiersze wniosku o transport” w sekcji **Popyt i podaż** na stronie **Warsztat planowania wysyłki ładunku**. Następnie można dodać te dwa wiersze do nowego ładunku. Nowy ładunek będzie zawierał oba wiersze zamówienia sprzedaży oraz będzie miał centrum jako adres „odbioru”, a odbiorcę A jako miejsce docelowe „dostawy”. Następnie wszystkie trzy ładunki są gotowe do ustawienia stawek i wyznaczenia tras jak każdy inny ładunek. Dla każdego ładunku można wybrać dowolnego przewoźnika proponowanego przez system. [![Konsolidacja centrum](./media/hubconsol.jpg)](./media/hubconsol.jpg) Tej samej metody można używać do konsolidowania ładunków dla wielu zamówień przeniesienia. W takim przypadku odbiorca A na powyższym diagramie jest magazynem. Alternatywnie można konsolidować ładunki dla wielu zamówień zakupu, jeżeli ładunki są dostarczane od różnych dostawców do tego samego magazynu. Można mieć więcej niż jedno centrum konsolidacji oraz konsolidować w wielu centrach w przypadku większej ilości ładunków pochodzących z różnych magazynów. Gdy skompilujesz podstawowe ładunki i włączysz opcję konsolidacji w centrum, nowe ładunki tworzysz przy użyciu wierszy wniosku o transport skonsolidowany. Następnie ustawiasz stawki i rozsyłasz ładunki.





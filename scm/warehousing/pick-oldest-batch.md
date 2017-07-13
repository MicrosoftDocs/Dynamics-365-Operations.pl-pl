---
title: "Pobieranie najstarszej partii na urządzeniu przenośnym"
description: "W tym temacie opisano sposób konfigurowania i stosowania opcji pobierania najstarszej partii z urządzenia przenośnego."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: ee45fed40b10dbe913c73e1186b726a39831816d
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Pobieranie najstarszej partii na urządzeniu przenośnym
<a id="pick-oldest-batch-on-a-mobile-device" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Dostęp do konfiguracji **Pobierz z najstarszej partii** można uzyskać z menu urządzenia przenośnego, a następnie ustawić w niej wymuszanie lub ostrzeganie pracowników magazynu, aby pobierali najstarszą partia w swojej obecnej lokalizacji.  

## Zastosowanie
<a id="where-it-applies" class="xliff"></a>
Funkcjonalność pobierania najstarszej partii jest konfigurowana w menu urządzenia przenośnego i wpływa na pobieranie towarów w partiach poniżej.

## Konfigurowanie pobierania najstarszej partii
<a id="how-to-set-up-the-configuration-for-pick-oldest-batch" class="xliff"></a> 
Dla towarów skonfigurowanych do wykorzystywania istniejącej pracy w opcji **Pobierz z najstarszej partii** na urządzeniu komórkowym można ustawić wartość **Brak**, **Ostrzegaj** lub **Wymuszaj**.

**Brak**: Pracownicy nie będą dostawać żadnych komunikatów i mogą pobierać dowolne partie w swoich lokalizacjach.

**Ostrzegaj** i **Wymuszaj**: Gdy pracownik zaznaczy partię, nad formantem partii będzie wyświetlana lista partii z najstarszymi datami ważności. Jeśli lokalizacja jest kontrolowana przez numer identyfikacyjny, nad formantem numeru identyfikacyjnego zostanie wyświetlona lista numerów identyfikacyjnych z najstarszymi partiami. 
-   **Ostrzeganie**: Jeśli pracownik wybierze numer identyfikacyjny lub partię, która nie znajduje się na wyświetlanej liście, formant będzie wygaszony i pojawi się ostrzeżenie, że istnieje starsza partia do wybrania. Aby móc kontynuować pracę, pracownik może ponownie wybrać ten sam numer identyfikacyjny lub partię.  
-   **Wymuszaj**: Pracownicy będą cały czas otrzymywać komunikat, że istnieje starsza partia do pobrania.


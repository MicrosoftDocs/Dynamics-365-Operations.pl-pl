---
title: Pobieranie najstarszej partii na urządzeniu przenośnym
description: W tym temacie opisano sposób konfigurowania i stosowania opcji pobierania najstarszej partii z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8e0deadaeb403e1f645309a141c5678fbe3f716
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232894"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Pobieranie najstarszej partii na urządzeniu przenośnym

[!include [banner](../includes/banner.md)]

Dostęp do konfiguracji **Pobierz z najstarszej partii** można uzyskać z menu urządzenia przenośnego, a następnie ustawić w niej wymuszanie lub ostrzeganie pracowników magazynu, aby pobierali najstarszą partia w swojej obecnej lokalizacji.  

## <a name="where-it-applies"></a>Zastosowanie
Funkcjonalność pobierania najstarszej partii jest konfigurowana w menu urządzenia przenośnego i wpływa na pobieranie towarów w partiach poniżej.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Konfigurowanie pobierania najstarszej partii 
Dla towarów skonfigurowanych do wykorzystywania istniejącej pracy w opcji **Pobierz z najstarszej partii** na urządzeniu komórkowym można ustawić wartość **Brak**, **Ostrzegaj** lub **Wymuszaj**.

**Brak**: Pracownicy nie będą dostawać żadnych komunikatów i mogą pobierać dowolne partie w swoich lokalizacjach.

**Ostrzegaj** i **Wymuszaj**: Gdy pracownik zaznaczy partię, nad formantem partii będzie wyświetlana lista partii z najstarszymi datami ważności. Jeśli lokalizacja jest kontrolowana przez numer identyfikacyjny, nad formantem numeru identyfikacyjnego zostanie wyświetlona lista numerów identyfikacyjnych z najstarszymi partiami. 
-   **Ostrzeganie**: Jeśli pracownik wybierze numer identyfikacyjny lub partię, która nie znajduje się na wyświetlanej liście, formant będzie wygaszony i pojawi się ostrzeżenie, że istnieje starsza partia do wybrania. Aby móc kontynuować pracę, pracownik może ponownie wybrać ten sam numer identyfikacyjny lub partię.  
-   **Wymuszaj**: Pracownicy będą cały czas otrzymywać komunikat, że istnieje starsza partia do pobrania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
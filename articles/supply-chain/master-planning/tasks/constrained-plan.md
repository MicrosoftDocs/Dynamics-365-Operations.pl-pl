---
title: Generowanie planu z ograniczeniami
description: W tym artykule pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i wydajności.
author: t-benebo
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65884d556724cd6132fe328e95a5bec78885c174
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904022"
---
# <a name="generate-a-constrained-plan"></a>Generowanie planu z ograniczeniami

[!include [banner](../../includes/banner.md)]

W tym artykule pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i wydajności. Plan gwarantuje, że produkcja nie rozpocznie się przed zapewnieniem dostępności materiałów i wyeliminowaniem ryzyka nadrezerwacji. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla planisty produkcji.


## <a name="set-up-a-constrained-plan"></a>Konfigurowanie planu z ograniczeniami
1. Na stronie głównej wybierz obszar roboczy **planowania głównego**.
2. Wybierz **Plany główne** z listy łączy znajdujących się po prawej stronie obszaru roboczego.
3. Na liście znajdź i zaznacz odpowiedni rekord. Przykład: **Plan statyczny**.  
4. W polu **Ograniczone zdolności produkcyjne** wybierz opcję **Tak**.
5. W polu **Horyzont czasowy ograniczonych zdolności produkcyjnych** wpisz `30`.
6. Rozwiń sekcję **Horyzonty czasowe w dniach**.
7. W polu **Zdolności produkcyjne** wybierz opcję **Tak**.
8. W polu **Horyzont czasowy planowania zdolności produkcyjnych (dni)** wpisz liczbę dni. Przykład: `60`  
9. W polu **Obliczone opóźnienia** zaznacz opcję **Tak**.
10. W polu **Oblicz horyzont czasowy opóźnień (dni)** wpisz liczbę. Przykład: `60` 
11. Rozwiń sekcję **Obliczone opóźnienia**.
12. W każdym polu **Dodaj obliczone opóźnienie do daty zapotrzebowania** zaznacz opcję **Tak**.
13. Zamknij stronę.

## <a name="create-a-constrained-plan"></a>Tworzenie planu z ograniczeniami
1. Wybierz opcję **Uruchom**.
2. W polu **Plan główny** wprowadź lub wybierz plan, dla którego skonfigurowano ograniczenia.  
3. Kliknij przycisk **OK**.
4. Wybierz **Zamówienia planowane**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
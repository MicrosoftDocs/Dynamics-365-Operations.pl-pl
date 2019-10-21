---
title: Ustawianie unikatowości separatora '
description: W tym temacie wyjaśniono, dlaczego nie można mieć tego samego separatora dla planu kont i wartości wymiarów. Po uaktualnieniu należy zmienić wartości separatora.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 2622245c7ce7213665ab32f4020c282df28cb886
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248787"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Ustawianie unikatowości ogranicznika planu kont

[!include [banner](../includes/banner.md)]

W Microsoft Dynamics AX 2012 można używać tego samego separatora dla planu kont i wartości wymiarów. W obecnej wersji Finance and Operations nie można mieć tego samego separatora dla planu kont i wartości wymiarów. W razie istnienia zduplikowanych separatorów można je zmienić po uaktualnieniu. 

Ta funkcja jest dostępna w następujących wersjach:
- Finance and Operations w wersji 8.0
- Finance and Operations w wersji 7.1 z poprawką KB 4094701 Nie można wprowadzić wymiarów finansowych, jeśli wartości wymiarów zawierają separator planu kont
- Finance and Operations wersja 7.2 z poprawką KB 4092967 Nie można wybrać podprojektu jako wymiaru, jeśli format podprojektu zawiera separator wymiaru

## <a name="update-delimiter"></a>Aktualizacja separatora
Jeśli występuje konflikt z planem kont, można zmienić separator planu kont i format identyfikatora projektu/podprojektu. Nie można zmieniać żadnych innych separatorów wymiarów. 
- Separator planu kont można zmienić po uaktualnieniu ustawieniu **Parametry księgi głównej** > **Plan kont i wymiary** > **Zmień separator**. 
- Jeśli jedyny konflikt występuje z formatem identyfikatora projektu/podprojektu, można zmienić tę wartość w ustawieniu **Parametry modułu Zarządzanie projektami i ich księgowanie** > **Ogólne** > **Modyfikuj format podprojektu**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Jak ustalić, czy środowisko wymaga aktualizacji separatorów 
Jeśli separatory w uaktualnionym środowisku powodują konflikt, może występować niestabilność podczas wprowadzania wartości w formancie wpisu podzielonego na segmenty lub formacie wprowadzania wymiarów. Oznacza to, że trzeba będzie zawsze używać wyszukiwań lub wysuwanych menu podczas wprowadzania kombinacji wymiarów i kont.

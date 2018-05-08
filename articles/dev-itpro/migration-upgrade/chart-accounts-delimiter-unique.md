---
title: "Ogranicznik planu kont musi być unikatowy"
description: "W programie Dynamics 365 for Finance and Operations nie można mieć tego samego separatora dla planu kont i wartości wymiarów. Po uaktualnieniu należy zmienić wartości separatora."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c9728714944b54f3bff1e2a8b43c7adcf5200f08
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="chart-of-accounts-delimiter-must-be-unique"></a>Ogranicznik planu kont musi być unikatowy

[!include [banner](../includes/banner.md)]

W programie Microsoft Dynamics AX 2012 można używać tego samego separatora dla planu kont i wartości wymiarów. W programie Dynamics 365 for Finance and Operations nie można mieć tego samego separatora dla planu kont i wartości wymiarów. W razie istnienia zduplikowanych separatorów można je zmienić po uaktualnieniu. 

Funkcja jest dostępna w następujących programach:
- Dynamics 365 for Finance and Operations wersja 8.0
- Dynamics 365 for Finance and Operations wersja 7.1, z poprawką KB 4094701 Nie można wprowadzić wymiarów finansowych, jeśli wartości wymiarów zawierają separator planu kont
- Dynamics 365 for Finance and Operations wersja 7.2, z poprawką KB 4092967 Nie można wybrać podprojektu jako wymiaru, jeśli format podprojektu zawiera separator wymiaru

## <a name="update-delimiter"></a>Aktualizacja separatora
Jeśli występuje konflikt z planem kont, można zmienić separator planu kont i format identyfikatora projektu/podprojektu. Nie można zmieniać żadnych innych separatorów wymiarów. 
- Separator planu kont można zmienić po uaktualnieniu do programu Finance and Operations w ustawieniu **Parametry księgi głównej** > **Plan kont i wymiary** > **Zmień ogranicznik**. 
- Jeśli jedyny konflikt występuje z formatem identyfikatora projektu/podprojektu, można zmienić tę wartość w ustawieniu **Parametry modułu Zarządzanie projektami i ich księgowanie** > **Ogólne** > **Modyfikuj format podprojektu**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Jak ustalić, czy środowisko wymaga aktualizacji separatorów 
Jeśli separatory w uaktualnionym środowisku powodują konflikt, może występować niestabilność podczas wprowadzania wartości w formancie wpisu podzielonego na segmenty lub formacie wprowadzania wymiarów. Oznacza to, że trzeba będzie zawsze używać wyszukiwań lub wysuwanych menu podczas wprowadzania kombinacji wymiarów i kont.


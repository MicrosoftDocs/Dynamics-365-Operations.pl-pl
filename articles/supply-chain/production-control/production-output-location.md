---
title: Lokalizacja wyjściowa produkcji
description: W tym artykule opisano hierarchię używaną do identyfikowania lokalizacji wyjściowej produkcji.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 130db343c4d09f2b8d31bf8acad3dcceec2be32e
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067950"
---
# <a name="production-output-location"></a>Lokalizacja wyjściowa produkcji

[!include [banner](../includes/banner.md)]

W tym artykule opisano hierarchię używaną do identyfikowania lokalizacji wyjściowej produkcji.

Lokalizacja wyjściowa produkcji to lokalizacja, w której najpierw umieszcza się wyrób gotowy bezpośrednio po ukończeniu produkcji. Zazwyczaj znajduje się blisko miejsca wytwarzania. Lokalizacja wyjściowa produkcji jest wykorzystywana jako pośredni magazyn materiału, zanim zostanie on przeniesiony do obszaru wysyłki, miejsca składowania, lokalizacji wejściowej produkcji następnego procesu produkcji, itd. 

Domyślną lokalizację wyjściową produkcji ustawia się podczas zgłaszania wyrobów gotowych względem zlecenia produkcyjnego lub szarży produkcyjnej. Do identyfikowania tej lokalizacji wyjściowej jest używana hierarchii przedstawiona poniżej:

1. Używanie lokalizacji wyjściowej zdefiniowanej w nagłówku zlecenia produkcyjnego lub szarży produkcyjnej.
2. Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w zasobie wykorzystywanym przez ostatnią operację zdefiniowaną w marszrucie produkcji.
3. Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w grupie zasobów wykorzystywanej przez zasób w ostatniej operacji zdefiniowanej w marszrucie produkcji.
4. Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w magazynie zdefiniowanym dla zlecenia produkcyjnego.

Domyślna lokalizacja wyjściowa produkcji jest ustawiana tylko dla produktów skonfigurowanych przy użyciu funkcjonalności procesów magazynowych (WMS). Gdy towar tego typu jest zgłaszany jako gotowy, jest tworzona praca magazynowa typu **Ukończono odkładanie wyrobów** lub **Odłożenie produktu ubocznego i produktu towarzyszącego**. W tym typie pracy lokalizacja wyjściowa produkcji jest wykorzystywana jako lokalizacja pobrania. Lokalizacja odłożenia jest określana przez dyrektywy lokalizacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy
description: Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 96af593d2e8a738258fe614f0f252620cb48c5f19eeb4425c9659ee6f9cd8c0c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741220"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy

Numer artykułu z bazy wiedzy: 4614408

## <a name="symptoms"></a>Objawy

Ten problem występuje, gdy wymiar **magazynowy** nie jest przypisany na karcie **Wymiary prognozy** na stronie **parametrów prognozowania popytu**. Mimo tego kolumna **Magazyn** jest wyświetlana na stronie **Prognoza popytu** (**Planowanie główne \> Prognozowanie \> Element prognozy ręcznej \> Linie prognozy popytu**).

## <a name="resolution"></a>Rozdzielczość

Ustawienia na karcie **Wymiary prognozy** na stronie **Parametr prognozowania popytu** nie wpływają na stronę **Prognoza popytu**. Sterują one prognozą bazową, która jest generowana i wyświetlana w skorygowanej prognozie popytu. Nie kontrolują jednak wymiarów wymaganych dla „rzeczywistej” prognozy popytu. Autoryzując rekordy, które są widoczne na stronie **Skorygowana prognoza popytu**, można je przekonwertować na „rzeczywiste” wpisy prognozy dla modelu prognozy. Następnie można używać tego modelu do planowania głównego.

Na stronie **Prognoza popytu** wymiary prognozy rzeczywistej wyświetlane w wierszach prognozy popytu są częścią wymiarów magazynowych. (To zachowanie przypomina zachowanie wierszy zamówienia sprzedaży) Jeśli system nie jest ustawiony do używania **magazynu** jako obowiązkowego wymiaru magazynowego, stronę można dostosować w celu ukrycia kolumny.

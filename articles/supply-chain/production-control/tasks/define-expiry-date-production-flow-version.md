---
title: Definiowanie daty ważności wersji przepływu produkcji
description: Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97ac33d28a49ad0f2a3956ad65b159e4ec4785c7
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983261"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definiowanie daty ważności wersji przepływu produkcji

[!include [banner](../../includes/banner.md)]

Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji. Nie jest konieczne dezaktywowanie wersji.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Ustawianie daty ważności w celu zakończenia wersji przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz dowolny przepływ produkcji mający wersję, która jest już zdefiniowana.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. Na liście oznacz wybrany wiersz.
6. W polu Data wygaśnięcia wprowadź datę i godzinę.
    * Po upływie daty ważności nowa wersja nie rozpocznie się ani nie uaktywni. Nie będzie można również tworzyć ani uruchamiać zadań dla tego przepływu produkcji. Natomiast będzie można dokończyć rozpoczęte zadania.  


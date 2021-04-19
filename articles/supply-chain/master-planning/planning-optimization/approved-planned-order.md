---
title: Zatwierdzanie zamówień planowanych
description: W tym temacie opisano zatwierdzanie zamówień planowanych, które są obsługiwane podczas optymalizacji planowania.
author: ChristianRytt
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 6c215a89403f16336caae5c62cde6df469c4091c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825898"
---
# <a name="approve-planned-orders"></a>Zatwierdzanie zamówień planowanych

[!include [banner](../../includes/banner.md)]

Ten temat zawiera informacje dotyczące aktualizowania stanu zamówień planowanych w optymalizacji planowania.

Należy zauważyć, że zatwierdzanie zamówień planowanych jest opcjonalnym krokiem w celu utworzenia zaakceptowanego zamówienia na podstawie zamówienia planowanego. Zaleca się zatwierdzanie zmodyfikowanych zamówień planowanych, w przeciwnym razie zmiany zostaną zignorowane i zastąpione przez następny przebieg planowania.

![Przepływ zamówienia planowanego](media/approved-planned-orders-1.png)

**Pole stanu** umożliwia oznakowanie postępu przy użyciu następujących wartości:

- **Nieprzetworzone:** Zamówienia planowane generowane podczas planowania głównego mają stan *Nieprzetworzone*. Zamówienia planowane o tym stanie zostaną usunięte podczas następnego uruchomienia planowania.
- **Ukończono:** Jeśli użytkownik zdecyduje się nie akceptować zamówienia planowanego, może zmienić stan na *Zakończone*, aby zaznaczyć, że zakończyła się ocena tego zamówienia planowanego. Należy zauważyć, że stan *Nieprzetworzone* i *Zakończone* jest traktowany tak samo przez system.
- **Zatwierdzone:** Jeśli chcesz zachować zmiany lub zaakceptować zamówienie planowane, zmień stan na *Zatwierdzone*. Zamówienia planowane ze stanem *Zatwierdzone* są uważane za ustalone w określonej ilości w planowaniu głównym, więc nie można ich modyfikować ani usuwać podczas późniejszego przebiegu planowania głównego. Aby to osiągnąć, logika planowania kopiuje *zatwierdzone* zamówienia planowane ze starej wersji planu do nowej wersji planu podczas planowania głównego. Należy zauważyć, że *Zatwierdzone* zamówienia planowane są uznawane za dostawę tylko w ramach określonego planu głównego.

Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Potwierdzenie partii i numeru identyfikacyjnego
description: W tym temacie opisano sposób konfigurowania i stosowania funkcjonalności potwierdzania partii i numeru identyfikacyjnego z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97790b91d4de536b89b580c26ef1e37145f7d7c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977445"
---
# <a name="batch-and-license-plate-confirmation"></a>Potwierdzenie partii i numeru identyfikacyjnego

[!include [banner](../includes/banner.md)]

Funkcja potwierdzania partii umożliwia potwierdzenie, że na urządzeniu komórkowym jest wybierana poprawna partia. W początkowym pobraniu pracy tylko dla towarów w partii powyżej, gdzie określenie partia powyżej wskazuje, że zakres partii sięga wyżej niż lokalizacja w hierarchii wyszukiwania, należy sprawdzić, czy pobierana partia jest taka sama, jak partia w wierszu pracy.

Funkcja potwierdzania numeru seryjnego umożliwia potwierdzenie, że na urządzeniu komórkowym jest wybierany poprawny numer identyfikacyjny. Podczas pobierania pracy z lokalizacji pośredniej należy sprawdzić, czy pobierany numer identyfikacyjny jest taki sam, jak numer identyfikacyjny skojarzony z pracą. Jeśli praca rozpoczyna się od zeskanowania numeru identyfikacyjnego, ten krok potwierdzania zostanie pominięty.

## <a name="where-it-applies"></a>Zastosowanie

Potwierdzanie stosuje się w następujących sytuacjach:

- Potwierdzanie partii stosuje się do pierwotnych pobrań pracy dla towarów w partiach powyżej.
- Potwierdzanie numeru identyfikacyjnego stosuje się do pobrań z lokalizacji pośrednich.

> [!IMPORTANT]
> Uzupełnienie zapasów nie jest obsługiwane dla potwierdzenia numeru identyfikacyjnego. W przypadku wykonywania pracy uzupełniania zapasów nie jest tworzony etap potwierdzenia numeru identyfikacyjnego.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Konfigurowanie potwierdzanie partii i numeru identyfikacyjnego

Funkcjonalność potwierdzania partii i numeru identyfikacyjnego można skonfigurować z menu urządzenia komórkowego.

1. Na urządzeniu przenośnym w menu przejdź do pozycji Konfiguracja potwierdzenia pracy.  
1. Wybierz opcję potwierdzania partii lub numeru identyfikacyjnego. Obie opcje są dostępne dla pobrań typów pracy, w których nie włączono opcji automatycznego potwierdzania.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
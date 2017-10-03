---
title: "Przyjęcie mieszanego numeru identyfikacyjnego"
description: "W tym temacie opisano sposób używania funkcji przyjęć z mieszanych numerów identyfikacyjnych do rejestrowania i tworzenia pracy dla wielu towarów na urządzeniu komórkowym."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0e785d71e7ae3c5f60d36d8b190001b5e356c626
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="mixed-license-plate-receiving"></a>Przyjęcie mieszanego numeru identyfikacyjnego

[!include[banner](../includes/banner.md)]

Przyjęcie z mieszanych numerów identyfikacyjnych umożliwia zbudowanie numeru identyfikacyjnego zawierającego wiele towarów, zanim zarejestrujesz i utworzysz pracę odłożenia. 

Numer identyfikacyjny obejmujący wiele towarów nie musi być rozdzielany w doku rozładunkowym w celu zarejestrowania osobno każdego towaru. 

Jeśli wiersze dokumentu źródłowego są identyfikowane na podstawie przepływu towarów, można skanować kody kreskowe na etapie kontroli towarów. Jeśli w kodzie kreskowym są skonfigurowane ilość i jednostka miary (JM), towar i ilość zostaną automatycznie dodane do mieszanego numeru identyfikacyjnego, po czym nastąpi powrót do ekranu umożliwiającego zeskanowanie następnego towaru. Umożliwia to szybkie przeskanowanie wszystkich towarów bez konieczności potwierdzania każdego kroku. 

W przepływie przyjęcia z mieszanych numerów identyfikacyjnych można wyświetlić listę towarów, które już zostały zeskanowane do numeru identyfikacyjnego, i z tego okna zmodyfikować lub skorygować ilość towaru.

## <a name="where-it-applies"></a>Zastosowanie

Przyjęcie z mieszanych numerów identyfikacyjnych to przepływ przyjęcia na urządzeniu komórkowym służący do rejestrowania i tworzenia pracy dla wielu wierszy/towarów równocześnie. Jest to przydatne, jeśli przyjmujesz z przychodzących numerów identyfikacyjnych zawierających wiele towarów. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Konfigurowanie przyjęcia z mieszanych numerów identyfikacyjnych
Przyjęcie z mieszanych numerów identyfikacyjnych jest konfigurowane jako element menu w urządzeniu komórkowym.

Należy utworzyć nowy element menu z trybem Praca, który nie wykorzystuje istniejącej pracy, i ustawić jedną z następujących metod:

- Przyjęcie mieszanego numeru identyfikacyjnego
- Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego

Dostępne są następujące opcje identyfikujące wiersze dokumentu źródłowego: pozycja zamówienia zakupu, wiersz zamówienia zakupu, zamówienia zwrotu, pozycja zamówienia przeniesienia i wiersz zamówienia przeniesienia. Te opcje mogą zmieniać kolejność przyjęcia dla pojedynczego numeru identyfikacyjnego. Ostatnia opcja to według pozycji ładunku. Do numeru identyfikacyjnego można dodać wiele towarów, ale nie można się przełączać między różnymi ładunkami.


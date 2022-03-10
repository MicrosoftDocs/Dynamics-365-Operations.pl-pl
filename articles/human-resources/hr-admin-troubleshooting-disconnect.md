---
title: Klient rozłącza się
description: W tym temacie wyjaśniono, co należy zrobić, jeśli klient zostaje odłączony od własnego środowiska.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071142"
---
# <a name="client-disconnects"></a>Klient rozłącza się


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Szczegóły środowiska** 

Ten problem może występować we wszystkich środowiskach.
 
**Objaw** 

Odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego. Na komputerze odbiorcy jest wyświetlany jeden z następujących komunikatów o błędach:

- Twoje połączenie zostało utracone Kliknij przycisk Zamknij, aby kontynuować pracę.
- Prawdopodobnie doszło do utraty łączności sieciowej. Kliknij przycisk Ponów próbę, aby spróbować ponownie.

**Czerwona flaga**

Ten problem występuje często, gdy użytkownicy są w fazie implementacji, porównują informacje między środowiskami produkcyjnymi i testowymi i zapominają, że poruszają się między sesjami. Jeśli użytkownicy są na tym etapie, prawdopodobnie wystąpi ten problem.

**Wystawienie** 

**Typy przeglądarek:** Google Chrome, Internet Explorer oraz Microsoft Edge

Microsoft Dynamics 365 Human Resources rozłącza użytkowników, gdy są otwarte dwie różne sesje jednocześnie dla tego samego użytkownika i tego samego typu przeglądarki. (Na przykład użytkownik A wyświetla środowisko 1 i 2 środowiska w Chrome.) Nie ma znaczenia, czy użytkownik otworzy inne okna przeglądarki lub różne karty. Jeśli te same poświadczenia użytkownika są używane do logowania się zarówno w środowisku 1, jak i środowisku 2 w tym samym czasie w tym samym typie przeglądarki, moduł Human Resources rozłączy jedną z sesji.

**Rozwiązanie**

Upewnij się, że tylko jedno środowisko jest otwarte w danej chwili dla danego typu przeglądarki. Użytkownicy mogą otwierać wiele sesji w tym samym środowisku (to znaczy wiele kart w tej samej przeglądarce).

Użytkownicy, którzy chcą do przechodzić między dwiema środowiskami w tym samym czasie powinni otwierać każde środowisko w innym typie przeglądarki. (Na przykład użytkownik A może wyświetlić środowisko 1 w przeglądarce Chrome i środowisko 2 w Microsoft Edge).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

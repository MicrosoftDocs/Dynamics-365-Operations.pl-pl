---
title: "Klient aplikacji Talent rozłącza się"
description: "W tym temacie wyjaśniono, co należy zrobić, jeśli odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 4f96b986059c179268f8a96ea7e7725831a93524
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="talent-client-disconnects"></a>Klient aplikacji Talent rozłącza się

[!include [banner](includes/banner.md)]

**Szczegóły środowiska** 

Ten problem może występować we wszystkich środowiskach.
 
**Objaw** 

Odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego. Na komputerze odbiorcy jest wyświetlany jeden z następujących komunikatów o błędach:

- Twoje połączenie zostało utracone Kliknij przycisk Zamknij, aby kontynuować pracę.
- Prawdopodobnie doszło do utraty łączności sieciowej. Kliknij przycisk Ponów próbę, aby spróbować ponownie.

**Czerwona flaga**

Ten problem występuje często, gdy użytkownicy są w fazie implementacji, porównują informacje między środowiskami produkcyjnymi i testowymi i zapominają, że poruszają się między sesjami. Jeśli użytkownicy są na tym etapie, prawdopodobnie wystąpi ten problem.

**Wydaj** 

**Typy przeglądarki:** Google Chrome, Internet Explorer i Microsoft Edge

Platforma Microsoft Dynamics 365 for Talent rozłączenia użytkowników, gdy są otwarte dwie różne sesje jednocześnie dla tego samego użytkownika i tego samego typu przeglądarki. (Na przykład użytkownik A wyświetla środowisko 1 i 2 środowiska w Chrome.) Nie ma znaczenia, czy użytkownik otworzy inne okna przeglądarki lub różne karty. Jeśli te same poświadczenia użytkownika są używane do logowania się zarówno w środowisku 1, jak i środowisku 2 w tym samym czasie w tym samym typie przeglądarki, aplikacja Talent rozłączy jedną z sesji.

**Rozwiązanie**

Upewnij się, że tylko jedno środowisko jest otwarte w danej chwili dla danego typu przeglądarki. Użytkownicy mogą otwierać wiele sesji w tym samym środowisku (to znaczy wiele kart w tej samej przeglądarce).

Użytkownicy, którzy chcą do przechodzić między dwiema środowiskami w tym samym czasie powinni otwierać każde środowisko w innym typie przeglądarki. (Na przykład użytkownik A może wyświetlić środowisko 1 w przeglądarce Chrome i środowisko 2 w Microsoft Edge.)

--- 
title: "Delegowanie elementów pracy w przepływie pracy"
description: "Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a>Delegowanie elementów pracy w przepływie pracy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników. Ta procedura służy do takiego konfigurowania systemu, aby automatycznie delegował Twoje elementy pracy do innego użytkownika.



Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="set-up-automatic-delegation"></a>Ustawienie automatycznej delegacji
1. Wybierz kolejno opcje Wspólne > Ustawienia > Opcje użytkownika.
2. Kliknij kartę Przepływ pracy.
    * Upewnij się, że jest rozwinięta sekcja Delegacja.    Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane. Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.  
3. Kliknij przycisk Dodaj.
4. W polu Zakres wybierz opcję.
    * Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.    Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy. Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu Nazwa.    Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy. Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu Nazwa.  
5. W polu Delegowanie wybierz użytkownika, do którego chcesz delegować elementy pracy.
    * W polach Data/godzina rozpoczęcia i Data/godzina zakończenia określ, kiedy elementy pracy mają być automatycznie delegowane.  
6. W polu Data/godzina rozpoczęcia wprowadź datę i godzinę.
7. W polu Data/godzina zakończenia wprowadź datę i godzinę.
8. Aby aktywować regułę delegowania, zaznacz pole wyboru Włączone.
    * Jeśli w ustawieniu Zakres zaznaczysz wartość Moduł, należy wybrać moduł w polu Nazwa.    Jeśli w ustawieniu Zakres zaznaczysz wartość Przepływ pracy, w polu Nazwa należy wybrać konkretny przepływ pracy, który ma być delegowany.  
9. W polu Komentarz wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.



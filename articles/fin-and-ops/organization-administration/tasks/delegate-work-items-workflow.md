---
title: Delegowanie elementów pracy w przepływie pracy
description: Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509460"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegowanie pozycji pracy w przepływie pracy

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a>Ręczne delegowanie elementu pracy

Aby delegować pojedynczy element pracy, zaznacz opcję **Delegowanie** w menu **przepływu pracy**, a następnie wprowadź użytkownika, który ma być delegowany, wraz z komentarzem. To spowoduje ponowne przypisanie elementu pracy do tego użytkownika, umożliwiającego mu wykonywanie go.

## <a name="automatically-delegate-work-items"></a>Automatyczne delegowanie elementów pracy

Jeśli zamierzasz być poza biurem lub nie będziesz mieć możliwości wykonywania elementów pracy przez jakiś czas, możesz automatycznie delegować nowe elementy pracy innym użytkownikom na stronie **opcje użytkownika**.

### <a name="set-up-automatic-delegation"></a>Ustawienie automatycznej delegacji
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


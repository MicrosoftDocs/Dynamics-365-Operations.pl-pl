---
title: Delegowanie elementów pracy w przepływie pracy
description: Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72ffe8123203123b75ea424814393d73ea8f728078e9e34fe903e5944ec11cfb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749563"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegowanie pozycji pracy w przepływie pracy

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Ręczne delegowanie elementu pracy

Aby delegować pojedynczy element pracy, zaznacz opcję **Delegowanie** w menu **przepływu pracy**, a następnie wprowadź użytkownika, który ma być delegowany, wraz z komentarzem. To spowoduje ponowne przypisanie elementu pracy do tego użytkownika, umożliwiającego mu wykonywanie go.

## <a name="manually-delegate-multiple-work-items"></a>Ręczne delegowanie wielu elementów roboczych

Wiele elementów roboczych można delegować razem z poziomu strony **Przypisane do mnie elementy robocze**. Następujące typy przepływów pracy kwalifikują się do delegacji grupowej: przepływ pracy zatwierdzania umowy zakupu, przepływ pracy zamówienia zakupu, przegląd zapotrzebowania na zakup i przepływ pracy faktury od dostawcy. Funkcja **Delegowania wielu elementów roboczych** jest domyślnie wyłączona i można ją włączyć w menu **Obszary robocze > Zarządzanie funkcjami**. Aby uzyskać pomoc we włączaniu tej funkcji, skontaktuj się z administratorem systemu.
1.  Przejdź do **Typowe > Typowe > Elementy pracy > Elementy pracy przypisane do mnie**.
2.  Wybierz elementy pracy, które będą delegowane.
3.  Kliknij menu **Delegowanie elementów roboczych**.
4.  W polu **Użytkownik** wybierz użytkownika, do którego chcesz delegować elementy pracy.
5.  W polu **Komentarz** wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.
6.  Kliknij przycisk **Deleguj elementy pracy**, aby zakończyć delegację elementu pracy.

## <a name="automatically-delegate-work-items"></a>Automatyczne delegowanie elementów pracy

Jeśli zamierzasz być poza biurem lub nie będziesz mieć możliwości wykonywania elementów pracy przez jakiś czas, możesz automatycznie delegować nowe elementy pracy innym użytkownikom na stronie **opcje użytkownika**.

### <a name="set-up-automatic-delegation"></a>Ustawienie automatycznej delegacji
1. Wybierz kolejno opcje **Wspólne > Ustawienia > Opcje użytkownika**.
2. Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja Delegacja została rozwinięta. Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane. Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.  
3. Kliknij przycisk **Dodaj**.
4. W polu **Zakres** wybierz opcję:
    - Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.
    - Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy. Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu **Nazwa**.
    - Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy. Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu **Nazwa**.  
5. W pole **Nazwa**:
    - Dla zakresu **Modułu** wybierz moduł docelowy.
    - Dla zakresu **Przepływ pracy** wybierz docelowy przepływu pracy.
6. W polu **Delegacja** wybierz użytkownika, do którego chcesz delegować elementy pracy. W polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia** określ, kiedy elementy pracy mają być automatycznie delegowane.  
7. W polu **Data/godzina rozpoczęcia** wprowadź datę i godzinę.
8. W polu **Data/godzina zakończenia** wprowadź datę i godzinę.
9. Aby aktywować regułę delegowania, zaznacz pole wyboru **Włączone**. 
10. W polu **Komentarz** wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
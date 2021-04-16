---
title: Konfigurowanie przepływów pracy zatwierdzeń wynajmów
description: W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4d5416b3b24d5fbb3ac46afb3c672212d41d42d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827561"
---
# <a name="set-up-lease-approval-workflows"></a>Konfigurowanie przepływów pracy zatwierdzeń wynajmów

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu. Aby uzyskać więcej informacji o używaniu przepływu pracy, zobacz [Używanie przepływów pracy zatwierdzeń wynajmów](use-create-lease-wrkflw.md). 

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Przepływ pracy wynajmu**.
2. Na stronie **Przepływ pracy wynajmu** wybierz opcję **Nowe**.
3. W wyświetlonym oknie dialogowym w obszarze **Typ przepływu pracy** kliknij łącze **Przepływ pracy wynajmu**.

    Zostanie otwarta aplikacja. Gdy zostanie uruchomiona, zaloguj się w usłudze Azure Active Directory (Azure AD), a nastąpi przekierowanie do aplikacji przepływu pracy.

4. Przeciągnij element **Zatwierdzanie przepływu pracy wynajmu** do przepływu pracy.
5. Połącz jeden węzeł od elementu **Początek** do elementu **Zatwierdzanie przepływu pracy wynajmu**. Następnie połącz element **Zatwierdzanie przepływu pracy wynajmu** z elementem **Koniec**.
6. Kliknij dwukrotnie element **Zatwierdzanie przepływu pracy wynajmu**.
7. Wybierz opcję **Właściwości**, a następnie w obszarze **Ustawienia podstawowe** nadaj nazwę przepływowi pracy.

    Na tej stronie można również określić więcej parametrów przepływu pracy. Po włączeniu funkcji **Akcje automatyczne** system będzie automatycznie wykonywał określoną akcję. Powiadomienia mogą być wysyłane, jeśli są określone na karcie **Powiadomienia**. Na karcie **Ustawienia zaawansowane** można określić ostateczną osobę zatwierdzającą, ustawić limit czasu oraz wyznaczyć określone akcje do wykonania.

8. Po zakończeniu ustawiania parametrów przepływu pracy wybierz opcję **Zamknij**.
9. Wybierz kolejno opcje **Krok 1** i **Właściwości**.
10. W obszarze **Ustawienia podstawowe** wprowadź nazwę kroku, utwórz wiersz tematu dla zatwierdzenia oraz podaj instrukcje zatwierdzania.
11. Na stronie **Przypisanie** wybierz typ przypisania.
12. Aby przypisać konkretnych użytkowników do zatwierdzenia, wybierz opcję **Użytkownik**, wybierz użytkowników, którzy zatwierdzają umowy wynajmu, a następnie wybierz opcję **Zamknij**.
13. Wybierz opcję **Zapisz i zamknij**, aby utworzyć przepływ pracy. Następnie, po wyświetleniu monitu, wybierz przycisk **OK**.
14. Na stronie **Utwórz przepływ pracy** wybierz opcję **Zamknij**.
14. Zaznacz nowy przepływ pracy, a następnie wybierz opcję **Wersje**. Następnie wybierz opcję **Uaktywnij**, aby się upewnić, że przepływ pracy jest aktywny.
15. Kliknij przycisk **Zamknij**. Zostanie wyświetlona nowa aktywna wersja.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
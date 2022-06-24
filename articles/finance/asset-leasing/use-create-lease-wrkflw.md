---
title: Używanie przepływów pracy zatwierdzeń wynajmów
description: W tym artykule opisano sposób używania przepływów pracy do zatwierdzania umów wynajmu składników majątku oraz do śledzenia stanu i historii przepływów pracy.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4205b83919f0b3c30a4b5d8e3290af230f538f39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906450"
---
# <a name="use-lease-approval-workflows"></a>Używanie przepływów pracy zatwierdzeń wynajmów

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób używania przepływów pracy do zatwierdzania umów wynajmu składników majątku oraz do śledzenia stanu i historii przepływów pracy. Przepływy pracy wprowadzają spójność do zarządzania zatwierdzeniami umów wynajmu, wyznaczając standardowy zbiór kroków zatwierdzania i przypisując określonych użytkowników, którzy zatwierdzają każdy etap procesu. Osoba zatwierdzająca może zatwierdzić wynajem, odrzucić go, poprosić o jego modyfikację lub przypisać innemu użytkownikowi do zatwierdzenia. Przepływy pracy mogą również zwiększyć przejrzystość procesu zatwierdzania, umożliwiając śledzenie stanu i historii. Ponadto można wyświetlić scentralizowaną listę roboczą zawierającą zadania i zatwierdzenia przypisane do określonych osób zatwierdzających.

Przed użyciem tej procedury upewnij się, że utworzono co najmniej przepływ pracy zatwierdzania wynajmu. Jeśli nie istnieje przepływ pracy, utwórz go. Aby uzyskać więcej informacji o ustawianiu przepływu pracy, zobacz [Konfigurowanie przepływów pracy zatwierdzeń wynajmów](set-up-lease-wrkflw.md).

1. Prześlij umowę wynajmu do zatwierdzenia. Na stronie **Szczegóły księgi** dla wynajmu wybierz kolejno opcje **Przepływ pracy** i **Prześlij**.
2. W wyświetlonym oknie dialogowym można dodać komentarz. Wyznaczona osoba zatwierdzająca będzie widziała ten komentarz wraz z umową wynajmu. Po zakończeniu wprowadzania komentarza wybierz opcję **Prześlij**. Umowa wynajmu zostanie przesłana do systemu przepływu pracy, a osoba zatwierdzająca otrzyma ją do zatwierdzenia.
3. Aby wyświetlić umowy wynajmu przeznaczone do zatwierdzenia przez daną osobę, wybierz kolejno opcje **Moduły \> Wspólne \> Elementy pracy \> Elementy pracy przypisane do mnie**.
4. Na stronie **Elementy pracy przypisane do mnie** kliknij łącze **Identyfikator wynajmu** dla umowy wynajmu, którą chcesz wyświetlić. Wyświetlana strona zależy od ksiąg wynajmu i szczegółów wynajmu, do których masz dostęp.
5. Po zakończeniu oglądania umowy wynajmu wybierz opcję **Przepływ pracy** i zdecyduj, jakie działanie ma zostać wykonane. Dostępne opcje to **Zatwierdź**, **Odrzucone**, **Żądaj zmiany**, **Deleguj** i **Anulowane**. Można również wybrać opcję **Wyświetl historię**, aby wyświetlić historię zatwierdzania wybranej umowy wynajmu.
6. Po wybraniu akcji wprowadź komentarz, który ją opisuje. Po zakończeniu wprowadzania komentarza wybierz z listy akcję **Zatwierdzone**.
7. Aby wyświetlić akcje zatwierdzania, wróć do strony **Szczegóły wynajmu** ze strony **Podsumowanie wynajmu**, a następnie wybierz kolejno opcje **Przepływ pracy \> Wyświetl historię**.

    Działania przepływu pracy można przeglądać na stronie **Historia przepływu pracy**. Na tej stronie przedstawiono etapy przepływu pracy, które zostały wykonane w odniesieniu do danej umowy wynajmu. Można również używać pola **Elementy pracy** do obejrzenia stanu przypisanych elementów pracy.

8. Aby zatrzymać przepływ pracy, na stronie **Historia przepływu pracy** wybierz pozycję **Odwołaj**. W wyświetlonym oknie dialogowym wpisz komentarz, a następnie wybierz przycisk **OK**.
9. Aby dezaktywować przepływ pracy lub uaktywnić uprzednio utworzony przepływ pracy, wybierz kolejno opcje **Wynajem składnika majątku \> Ustawienia \> Przepływ pracy wynajmu**. Następnie na stronie **Przepływ pracy wynajmu** wybierz kolejno opcje **Przepływ pracy \> Wersje**. Aby bieżący przepływ pracy stał się nieaktywny, wybierz aktywną umowę wynajmu w oknie dialogowym wersji wynajmu, a następnie wybierz opcję **Dezaktywuj**. Aby uaktywnić istniejący przepływ pracy, wybierz przepływ pracy, a następnie wybierz opcję **Uaktywnij**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

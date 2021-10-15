---
title: Przepływy pracy zatwierdzania arkuszy magazynowych
description: W tym temacie opisano sposób konfigurowania i używania przepływów pracy zatwierdzania arkusza zapasów dla różnych typów transakcji dotyczących zapasów fizycznych. Przepływy pracy arkusza magazynowego zapewniają, że tylko zatwierdzone arkusze magazynowe mogą być księgowane w transakcjach.
author: yufeihuang
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d1bd846dae767b47280310fc8d9ca5ee82337ad
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568862"
---
# <a name="inventory-journal-approval-workflows"></a>Przepływy pracy zatwierdzania arkuszy magazynowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania i używania przepływów pracy zatwierdzania arkusza zapasów dla różnych typów transakcji dotyczących zapasów z natury, takich jak rozchody i przyjęcia, przesunięcia zapasów, listy materiałów (BOM) i uzgadnianie zapasów fizycznych. Przepływy pracy arkusza magazynowego zapewniają, że tylko zatwierdzone arkusze magazynowe mogą być księgowane w transakcjach.

> [!NOTE]
> Przepływy pracy zatwierdzania arkuszy magazynowych dotyczą tylko transakcji zarejestrowanych przy użyciu modułu Zarządzanie zapasami. Nie działają z arkuszami magazynowymi wyzwalanymi w module zarządzania magazynem.

## <a name="turn-on-the-inventory-journal-approval-workflows-feature"></a>Włączanie funkcji przepływów pracy zatwierdzania arkuszy magazynowych

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie zapasami i magazynem*
- **Nazwa funkcji:** *Przepływ pracy zatwierdzania arkusza magazynowego*

## <a name="create-your-inventory-journal-approval-workflows"></a>Utwórz przepływy pracy zatwierdzania arkusza zapasów

Aby skonfigurować tę funkcję, musisz utworzyć przepływ pracy dla każdego typu arkusza zapasów, który chcesz kontrolować. Ponieważ różne typy arkuszy magazynowych mogą mieć różne hierarchie zatwierdzania i kroki przepływu pracy, można skonfigurować indywidualne przepływy pracy dla każdego typu arkusza magazynowego.

Przepływy pracy obsługują kontrolę wersji, a każdy z nich ma identyfikator przepływu pracy i aktywną wersję. Możesz aktywować każdą nową wersję przepływu pracy natychmiast po utworzeniu lub pozostawić ją nieaktywną. Jeśli potrzebujesz różnych przepływów pracy dla tego samego typu arkusza, utwórz wiele przepływów pracy dla tego typu arkusza, a następnie przypisz każdy z nich do innej nazwy arkusza, która używa tego typu.

Aby utworzyć przepływy pracy zatwierdzania arkusza zapasów:

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Przepływy pracy w zakresie zarządzania zapasami**.
1. Wybierz pozycję **Nowy** w okienku akcji.
1. Umożliwia wybranie typu arkusza magazynowego, dla którego ma zostać skonfigurowany przepływ pracy:
    - **Arkusz zliczania znaczników zapasów**
    - **Arkusz zmian własności zapasów**
    - **Arkusz przesunięcia magazynowego**
    - **Arkusz przesunięć magazynowych**
    - **Arkusz inwentaryzacji zapasów**
    - **Arkusz BOM zapasów**
    - **Arkusz korekt zapasów**

    ![Okno dialogowe Tworzenie przepływu pracy.](media/journal-workflow-create-workflow.png "Okno dialogowe Tworzenie przepływu pracy")

1. Aplikacja edytora przepływu pracy jest uruchamiana na urządzeniu użytkownika. (Możesz zostać poproszony o zatwierdzenie tej akcji). Użyj go do zaprojektowania przepływu pracy w razie potrzeby. Aby uzyskać szczegółowe informacje dotyczące korzystania z edytora przepływu pracy, należy zapoznać się z tematem [Omówienie systemu przepływu pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. Po zapisaniu i zamknięciu aplikacji edytora przepływu pracy należy wybrać, czy aktywować tę wersję przepływu pracy, czy zachować ją jako nieaktywną.

> [!NOTE]
> Przepływy pracy udostępniają kontrolę wersji, co oznacza, że można wyświetlić listę utworzonych wersji i wybrać, które z nich są aktywne. Aby wyświetlić listę dostępnych wersji i wybrać, które mają zostać uaktywnione, wybierz przepływ pracy z listy na stronie **Przepływy pracy w zakresie zarządzania zapasami**. W okienku akcji otwórz kartę **Przepływ pracy** i wybierz opcję **Wersje**. W danym momencie dla każdego identyfikatora przepływu pracy może być aktywna tylko jedna wersja.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Przypisz przepływy pracy zatwierdzania do nazw arkuszy magazynowych

Następnym krokiem jest przypisanie przepływu pracy arkusza zapasów do każdej nazwy arkusza magazynowego. Dla każdego typu arkusza magazynowego można ustawić wiele nazw arkuszy magazynowych.

Aby skojarzyć przepływ pracy arkusza magazynowego z nazwą arkusza magazynowego:

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Nazwy arkuszy \> Zapasy**.
1. Wybierz nazwę arkusza z kolumny listy, aby otworzyć stronę ustawień.
1. Na skróconej karcie **Ogólne** ustaw opcje **Przepływ pracy zatwierdzania** na **Tak**. Kliknij **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie wyboru.

    ![Przypisz przepływ pracy do nazwy arkusza.](media/journal-workflow-journal-name.png "Przypisz przepływ pracy do nazwy arkusza")

1. Należy otworzyć listę rozwijaną **Przepływ pracy** i wybrać odpowiedni przepływ pracy. Lista przedstawia każdy aktywny przepływ pracy utworzony za pomocą aplikacji edytora przepływu pracy.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Tworzenie arkusza magazynowego i wysyłanie go do zatwierdzenia

Po powiązaniu nazwy arkusza magazynowego z odpowiadającym mu przepływem pracy zatwierdzania arkusza zapasów będzie można utworzyć nowe arkusze magazynowe, które używają tej nazwy, a następnie wysłać te arkusze do zatwierdzenia przy użyciu tego przepływu pracy. Nie będzie można zaksięgować arkusza zapasów, dopóki nie zostanie zatwierdzony przez osoby zatwierdzające skonfigurowane w przepływie pracy.

1. W okienku nawigacji rozwiń **Zarządzanie zapasami \> Wpisy w arkuszu \> Elementy**, a następnie wybierz typ arkusza magazynowego.
1. Wybierz opcję **Nowy**, aby utworzyć nowy arkusz o wybranym typie.
1. Zostanie otwarte okno dialogowe **Tworzenie arkusza magazynowego**. W razie potrzeby wypełnij formularz, a następnie kliknij przycisk **OK**, aby zapisać arkusz.
1. Wypełnij arkusz zgodnie z wymaganiami.
1. Podczas tworzenia lub otwierania arkusza magazynowego z skojarzonym przepływem zatwierdzenia, przycisk **Przepływ pracy** jest aktywny w okienku akcji. Gdy zechcesz przesłać arkusz do zatwierdzenia, wybierz przycisk **Przepływ pracy**, aby otworzyć okno dialogowe rozwijane, a następnie wybierz opcję **Prześlij**. Żądanie zatwierdzenia zostanie następnie skierowane do odpowiedniej osoby zatwierdzającej, która zostanie powiadomiona za pomocą metody powiadamiania skonfigurowanej dla przepływu pracy.

    ![Przesyłanie arkusza do zatwierdzenia.](media/journal-workflow-inventory-journal.png "Przesyłanie arkusza do zatwierdzenia")

Aby odwołać żądanie zatwierdzenia, otwórz odpowiedni arkusz, wybierz przycisk **Przepływ pracy**, a następnie wybierz pozycję **Odwołaj**. Spowoduje to zresetowanie przepływu pracy.

Po zatwierdzeniu arkusza będzie można go zaksięgować. Aby zaksięgować arkusz, wybierz pozycję **Księguj** z okienka akcji. Jeśli przycisk **Księguj** nie jest aktywny, arkusz nie został jeszcze zatwierdzony.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Odpowiadanie na żądanie zatwierdzenia arkusza magazynowego

Jeśli jesteś osobą zatwierdzającą, powinieneś otrzymywać wiadomość za każdym razem, gdy wymagane jest zatwierdzenie (zgodnie z konfiguracją w odpowiednim przepływie pracy). Następnie można zatwierdzić lub odrzucić żądanie zatwierdzenia arkusza, wykonując następujące czynności:

1. W okienku nawigacji rozwiń **Zarządzanie zapasami \> Wpisy w arkuszu \> Elementy**, a następnie wybierz typ arkusza magazynowego.
1. Otwórz odpowiedni arkusz i przejrzyj go.
1. W okienku akcji wybierz przycisk **Przepływu pracy**, aby otworzyć okno dialogowe rozwijane. Należy wybrać jedną z następujących opcji:
    - **Zatwierdź** - aby zatwierdzić wniosek.
    - **Odrzuć** - umożliwia odrzucenie odrzucenia żądania.
    - **Więcej \> Zmiana żądania** - Wysłanie wiadomości do żądającego z prośbą o zmianę czegoś konkretnego, a następnie ponowne przesłanie.
    - **Więcej \> Deleguj** — delegowanie zatwierdzenia innemu użytkownikowi.
    - **Więcej \> Odwołaj** - aby odwołać żądanie zatwierdzenia (resetuje przepływ pracy).
    - **Więcej \> Historia przepływu pracy** - aby wyświetlić historię tego przepływu pracy zatwierdzania.

## <a name="review-the-approval-history"></a>Przejrzyj historię zatwierdzania

Podobnie jak w przypadku innych typów przepływów pracy, można skorzystać ze strony **Historia przepływu pracy**, aby wyświetlić historię przepływów pracy zatwierdzania dla każdego arkusza.

Aby przejrzeć historię przepływu pracy dla arkusza:

1. W okienku nawigacji rozwiń **Zarządzanie zapasami \> Wpisy w arkuszu \> Elementy**, a następnie wybierz typ arkusza magazynowego.
1. Otwórz odpowiedni arkusz.
1. W okienku akcji wybierz przycisk **Przepływu pracy**, aby otworzyć okno dialogowe rozwijane. Wybierz **Historia przepływu pracy**. Aby uzyskać więcej informacji, zobacz [Wyświetl historię przepływu pracy](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Nie można znaleźć okna dialogowego „Przepływ pracy” dla arkuszy magazynowych
description: Nie można znaleźć okna dialogowego „Przepływ pracy” na stronie arkusza lub powiązane operacje przepływu pracy są niedostępne
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477290"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Nie można znaleźć okna dialogowego „Przepływ pracy” dla arkuszy magazynowych

## <a name="symptoms"></a>Objawy

Nie można znaleźć okna dialogowego **Przepływ pracy** na stronie arkusza lub powiązane operacje przepływu pracy są niedostępne.

Ten problem może mieć trzy przyczyny, co opisano w poniższych sekcjach.

## <a name="resolution-1"></a>Rozwiązanie 1

Jeśli problem dotyczy wszystkich użytkowników, może on wystąpić, ponieważ przepływ pracy zatwierdzania nie został przypisany do nazwy arkusza. Aby naprawić problem, należy wykonać następujące czynności.

1. Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Nazwy arkuszy &gt; Zapasy**.
1. W okienku listy wybierz nazwę arkusza, aby otworzyć jego ustawienia.
1. Na skróconej karcie **Ogólne** ustaw opcję **Przepływ pracy zatwierdzania** na *Tak*. Wybierz **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie zmiany.
1. W polu **Przepływ pracy** wybierz przepływ pracy do użycia dla wybranej nazwy arkusza.

## <a name="resolution-2"></a>Rozwiązanie 2

Jeśli w przepływie pracy jest używany dostosowany kod, problemy mogą wystąpić po uaktualnieniu systemu. Na przykład w przepływie pracy arkusza przycisk **Prześlij** może być wyszarzony, więc nie można go wybrać w celu zatwierdzenia przesłania.

Jeśli przycisk **Prześlij** jest wyszarzony, być może przepływ pracy został dostosowany, co oznacza, że metoda przepływu pracy `canSubmitToWorkflow()` w `FormDataUtil` została rozszerzona. Aby rozwiązać ten problem, zmień sposób rozszerzania metody `canSubmitToWorkflow()` w celu używania struktury w poniższym przykładzie.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Rozwiązanie 3

Jeśli problem dotyczy tylko kilku określonych użytkowników, użytkownicy ci mogą nie mieć uprawnień zabezpieczeń wymaganych do uruchamiania operacji przepływu pracy w arkuszach magazynowych. Sprawdź, czy każdy z tych użytkowników ma uprawnienie zabezpieczeń *Obsługa przepływu pracy arkusza magazynowego*. Domyślnie to uprawnienie jest przypisywane do obowiązków o takiej samej nazwie i jest stosowane do ról *Pracownik magazynu* i *Menedżer magazynu*.

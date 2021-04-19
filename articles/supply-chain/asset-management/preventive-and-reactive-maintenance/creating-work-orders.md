---
title: Tworzenie zlecenia pracy
description: W tym temacie opisano tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836741"
---
# <a name="creating-work-orders"></a>Tworzenie zlecenia pracy

[!include [banner](../../includes/banner.md)]

Po zaplanowaniu zadań konserwacji zapobiegawczej następnym krokiem jest utworzenie dla nich zleceń pracy. Ten krok można wykonać, korzystając z jednego z harmonogramów konserwacji. Zaplanowane zadania w harmonogramie konserwacji mogą mieć różne typy odwołań, jak opisano w poniższej tabeli.

| Typ odwołania | opis |
|---|---|
| Plany konserwacji | Zadania konserwacji zapobiegawczej oparte na planie konserwacji typu *Czas* lub *Licznik*. |
| Serie czynności konserwacyjnych | Zadania profilaktycznej obsługi technicznej, które zawierają kilka składników majątku, które wymagają podobnego typu obsługi. |
| Żądanie konserwacji | Ręcznie utworzone żądanie konserwacji lub naprawy składnika majątku. To żądanie można przekonwertować na zlecenie pracy. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Tworzenie zleceń pracy na podstawie harmonogramu konserwacji

Aby utworzyć zlecenia pracy na podstawie harmonogramu konserwacji, należy wykonać następujące kroki.

1. Otwórz jedną z następujących stron w zależności od sposobu wybierania pozycji planowania dla zleceń pracy:

    - Wszystkie harmonogramy konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Wszystkie harmonogramy konserwacji)**
    - Otwarte wiersze harmonogramu konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Otwarte wiersze harmonogramu konserwacji)**
    - Otwarte pule harmonogramu konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Otwarte pule harmonogramu konserwacji)**

1. W siatce zaznacz pole wyboru przy każdym zaplanowanym zadaniu konserwacji, dla którego chcesz utworzyć zlecenie pracy. Następnie w okienku akcji wybierz opcję **Zlecenie pracy**.

    Zostanie wyświetlone okno dialogowe **Tworzenie zleceń pracy**. W polu **Godziny prognozy konserwacji** zostanie wyświetlona liczba godzin prognozowanych dla wybranych wierszy.

    ![Okno dialogowe Tworzenie zleceń pracy](media/18-preventive-maintenance.png)

1. W sekcji **Parametry** określ liczbę zleceń pracy, które mają zostać utworzone. Umożliwia wybranie jednej z następujących opcji:

    - **Jedno zlecenie pracy na wiersz** — należy utworzyć jedno zlecenie pracy na wiersz harmonogramu konserwacji.
    - **Jedno zlecenie na** — należy utworzyć zlecenia pracy pogrupowane zgodnie z ustawieniami innych opcji, które stają się dostępne po wybraniu tej opcji.

1. W polu **Typ zlecenia pracy** wybierz typ zlecenia, który będzie używany dla wszystkich tworzonych zleceń pracy.
1. Wybierz przycisk **OK**, aby utworzyć zlecenia zgodnie z ustawieniami.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Grupowanie wierszy zlecenia pracy tworzonych automatycznie podczas planowania konserwacji

Ta funkcja umożliwia definiowanie reguł grupowania wierszy zleceń pracy w ramach pojedynczego zlecenia, gdy system jest tak ustawiony, aby generował zlecenia pracy automatycznie na podstawie planu konserwacji. Wcześniej generowane automatycznie zlecenia pracy mogły zawierać tylko jeden wiersz. Teraz jednak można grupować zlecenia według na przykład składnika majątku, typu składnika majątku lub lokalizacji czynności. (Ręcznie wygenerowane zlecenia pracy można już grupować w ten sposób, zgodnie z opisem w poprzedniej sekcji tego tematu).

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Włącz grupowanie dla automatycznie generowanych zleceń pracy

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie składnikami majątku*
- **Nazwa funkcji:** *Stosowanie reguł grupowania zleceń pracy podczas uruchamiania planu konserwacji*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Konfiguruj grupowanie dla automatycznie generowanych zleceń pracy

Aby skonfigurować grupowanie dla automatycznie generowanych zleceń pracy, wykonaj następujące kroki.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Konserwacja zapobiegawcza \> Plany konserwacji**.
1. Dla każdego planu, w którym mają być generowane pogrupowane zlecenia pracy, wykonaj następujące czynności:

    1. Wybierz plan w okienku listy.
    1. Upewnij się, że na skróconej karcie **Wiersze** jest zaznaczone pole wyboru **Automatycznie utwórz** w każdym wierszu.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Okresowe \> Konserwacja zapobiegawcza \> Planowanie planów konserwacji**.
1. W oknie dialogowym **Planowanie planów konserwacji** w sekcji **Okres** określ horyzont czasowy planu (jak daleko w przyszłości będą wyszukiwane zaplanowane zadania konserwacji, dla których mają zostać wygenerowane prace).
1. Ustaw opcję **Automatycznie utwórz zlecenie pracy z harmonogramu** na *Tak*.
1. W sekcji **Zlecenie pracy** wybierz jedną z następujących opcji:

    - **Jedno zlecenie pracy na wiersz** — należy utworzyć jedno zlecenie pracy na wiersz harmonogramu konserwacji. (Ta opcja udostępnia te same funkcje, które są dostępne, gdy funkcja *Stosowanie reguł grupowania zleceń pracy podczas uruchamiania planu konserwacji* jest wyłączona).
    - **Jedno zlecenie na** — należy utworzyć zlecenia pracy pogrupowane zgodnie z ustawieniami innych opcji, które stają się dostępne po wybraniu tej opcji.

1. Jeśli chcesz, aby opcje były stosowane podczas uruchamiania tylko niektórych planów konserwacji, na skróconej karcie **Rekordy do uwzględnienia** dodaj filtry zgodnie z potrzebami, tak jak w przypadku innych zadań wsadowych w aplikacji Microsoft Dynamics 365 Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** skonfiguruj wymagane opcje przetwarzania wsadowego i planowania, tak jak w przypadku innych zadań wsadowych w aplikacji Supply Chain Management.
1. Wybierz przycisk **OK**, aby uruchomić i/lub zaplanować wybrane plany konserwacji.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
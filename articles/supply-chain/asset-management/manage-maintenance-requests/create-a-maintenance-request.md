---
title: Utwórz żądania konserwacji
description: W tym temacie wyjaśniono, jak utworzyć żądanie konserwacji w zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: af67d320f14fc6c3d28eec47de402ba645eea06d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836789"
---
# <a name="create-maintenance-requests"></a>Utwórz żądania konserwacji

[!include [banner](../../includes/banner.md)]

 

Żądania konserwacji mogą być używane, jeśli pracownicy zajmujący się konserwacją lub pracownicy produkcyjni odkrywają, że sprzęt wymaga naprawy, ale nie można wykonać zadania naprawy od razu.

**Przykład:** gdy konserwator robi naprawę, odkrywa, że inny składnik majątku w tej samej lokalizacji musi być serwisowany. Konserwator nie ma jednak czasu ani wymaganych części zamiennych do wykonania naprawy. W związku z tym tworzy żądanie konserwacji składnika majątku i wprowadza krótki opis problemu.

Sekcja **Aktywne żądania konserwacji** w okienku **Powiązane informacje** po prawej stronie strony **Wszystkie składniki majątku** lub **Aktywne składniki majątku** (**Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**) zawiera aktywne żądania konserwacji, które są dołączone do wybranego składnika majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.
2. Wybierz pozycję **Nowy**.
3. W oknie dialogowym **Tworzenie żądania** w polu **Typ żądania konserwacji** wybierz typ żądania konserwacji. Sugerowany jest domyślny typ.
4. W polu **opis** wprowadź nazwę lub tytuł, który krótko opisuje żądanie konserwacji.
5. W polach **lokalizacja** i **składnik majątku** wybierz pozycję Lokalizacja czynności konserwacyjnych lub składnik majątku lub kombinację lokalizacji czynności konserwacyjnych i składnika majątku, zgodnie z Twoimi potrzebami. Można utworzyć żądanie konserwacji bez wybierania składnika majątku i można później dodać składnik majątku do żądania konserwacji. Jeśli konserwator, który jest zalogowany i jest powiązany z zasobem powiązanym ze składnikiem majątku, pole **Składnik majątku** jest automatycznie ustawiane.

    Jeśli żądanie konserwacji jest już dołączone do wybranego składnika majątku, na górze okna dialogowego **Utwórz żądanie** pojawi się pasek komunikatów informujący o identyfikatorze istniejącego żądania konserwacji. Pasek komunikatów powiadamia również o tym, czy składnik majątku jest objęty umową gwarancyjną.

6. W polu **poziom usługi** wybierz poziom usługi wskazujący pilność żądania.
7. Jeśli wybrano składnik majątku w kroku 5, można użyć **symptomów usterek**, **obszaru błędów** i **Typu usterki**, aby utworzyć rejestrację błędów.
8. Jeśli żądanie konserwacji spowodowało przerwę konserwacyjną, wprowadź datę rozpoczęcia i czas przerwy.

    Pole **rozpoczęte przez** jest automatycznie ustawiane jako Twoja nazwa użytkownika.

10. W polu **Rzeczywisty początek** zostanie automatycznie ustawiona bieżąca data i godzina. Można jednak zmienić jego wartość.
11. W polu **notatki** wprowadź wszelkie dodatkowe notatki, które są wymagane.
12. Kliknij przycisk **OK**.

![Utwórz żądanie konserwacji](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Późniejsze przetwarzanie żądań konserwacji

Po utworzeniu żądania konserwacji, ale zanim zostanie przekonwertowane na zlecenie pracy, konieczne jest zaktualizowanie różnych informacji. Zwykle planista lub inny pracownik administracyjny wykonuje to zadanie.

- Na stronie **wszystkie żądania konserwacji** lub **aktywne żądania konserwacji** wybierz żądanie do obsługi, a następnie wybierz pozycję **Edytuj.**

W widoku szczegółów można aktualizować różne informacje. Oto kilka przykładów:

- Wybierz i zweryfikuj składnik majątku. Jeśli musisz wybrać inny składnik majątku później, możesz ustawić opcję **zweryfikowany składnik majątku** jako **nie.**
- Wybierz odpowiedzialną grupę konserwatorów i/lub odpowiedzialnego konserwatora. Aby uzyskać więcej informacji o wymaganej konfiguracji, zobacz [odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).
- Wybierz typ zadania konserwacji i, jeśli te informacje są istotne, wariant zadania konserwacji i profesję zadania.
- W polach **szerokość** i **długość** geograficzna wprowadź współrzędne geograficzne. Wszystkie współrzędne, które są dodawane do żądania konserwacji są automatycznie przenoszone do powiązanego zlecenia pracy. 

![Aktualizuj żądanie konserwacji](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Jeśli wybierzesz składnik majątku podczas tworzenia żądania konserwacji, można dodać jeden błąd do zasobu. Po utworzeniu żądania konserwacji można dodać więcej błędów, zgodnie z żądaniem. Aby dodać błędy, wybierz opcję **błąd składnika majątku** na stronie **wszystkie żądania konserwacji**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Stany cyklu życia żądania konserwacji
description: W tym temacie opisano, jak konfigurować stany cyklu życia żądań konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3c2f717969b938d05e68ac775d31b6a5d5ec26a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022087"
---
# <a name="maintenance-request-lifecycle-states"></a>Stany cyklu życia żądania konserwacji

[!include [banner](../../includes/banner.md)]

 


Stany cyklu życia żądań konserwacji określają etapy, przez które może przejść żądanie. Przykładowe stany to **Utworzony**, **Aktywny** i **Włączony**. Jeśli żądanie konserwacji jest konwertowane na zlecenie pracy, stan cyklu życia żądania konserwacji musi zostać zaktualizowany do **Zakończony** lub **Zamknięty**, aby było możliwe wskazanie, że żądanie konserwacji nie jest już aktywne. Na stronie listy **Wszystkie żądania konserwacji** można wyświetlić wszystkie żądania konserwacji, niezależnie od ich stanu cyklu życia.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Ustawianie stanów cyklu życia żądania konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Stany cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć stan cyklu życia żądania konserwacji.
3. W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.
4. W polu **Nazwa** wprowadź nazwę.

    Na skróconej karcie **Szczegóły** pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia żądań konserwacji, które używają tego stanu cyklu życia.

5. Na skróconej karcie **Ogólne** ustaw opcję **Aktywne** na **Tak**, jeśli żądanie konserwacji powinno być aktywne w tym stanie cyklu życia.
6. Ustaw opcję **Ustaw rzeczywisty koniec** na **Tak**, jeśli rzeczywista data i godzina zakończenia powinny być automatycznie wprowadzane w żądaniu konserwacji, które znajduje się w tym stanie cyklu życia.
7. Ustaw opcję **Utwórz zlecenie pracy** na **Tak**, jeśli zlecenie pracy może być utworzone z żądania konwersacji w tym stanie cyklu życia.
8. Ustaw opcję **Usuń** na **Tak**, jeśli żądanie konserwacji można usunąć, gdy jest w tym stanie cyklu życia.
9. Na skróconej karcie **Aktualizacji** opcje **Przychodzące** i **Wychodzące** w sekcji **Składnik majątku** są odpowiednie, jeśli jest używana Naprawa magazynu. Należy wybrać odpowiednią opcję **Tak**, jeśli stan cyklu eksploatacji środków trwałych wybrany w żądaniu obsługi powinien być automatycznie aktualizowany na **Przychodzący** lub **Wychodzący**, jeśli stan cyklu życia żądania obsługi jest określony jako **Przychodzący** lub **Wychodzący**.

Na poniższej ilustracji pokazano przykład strony **Cykle życia żądań konserwacji**.

![Strona Stany cyklu życia żądania konserwacji](media/02-setup-for-requests.png)

> [!NOTE]
> Stany cyklu życia, grupy stanów cyklu życia oraz typy żądania konserwacji są powiązane i używane w taki sam sposób jak stany cyklu życia, grupy stanów cyklu życia oraz typy zlecenia pracy. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Ustawianie modeli cyklu życia żądania konserwacji

Po utworzeniu stanów cyklu życia, które są wymagane dla żądań konserwacji, można je podzielić na grupy stanu cyklu życia lub modele cyklu życia. Modele cyklu życia żądania konserwacji są używane do tworzenia przepływu, który może służyć do różnych typów żądań konserwacji. Jako minimum należy utworzyć jeden standardowy model cyklu życia lokalizacji żądania konserwacji.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Modele cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć model cyklu życia żądania konserwacji.
3. W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.
4. W polu **Nazwa** wprowadź nazwę.

    Na skróconej karcie **Szczegóły** pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia, które są wybrane w modelu cyklu życia. Pole **Typy żądania konserwacji** pokazuje liczbę typów żądania konserwacji, które używają tego modelu cyklu życia.

5. Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia, które powinny być uwzględnione w modelu cyklu życia:

    - Aby uwzględnić stanu cyklu życia w modelu cyku życia, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo](media/03-setup-for-requests.png), aby przenieść go do sekcji **Wybrane stany cyklu życia**.
    - Aby uwzględnić wszystkie dostępne stany cyklu życia w modelu cyklu życia, wybierz przycisk **Wybierz wszystkie dostępne stany** ![Wybierz wszystkie dostępne stany](media/04-setup-for-requests.png). Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.
    - Aby usunąć stan cyklu życia z modelu cyklu życia, wybierz go w sekcji **Wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki lewo ![Strzałka w lewo](media/05-setup-for-requests.png), aby przenieść go do sekcji **Pozostałe stany cyklu życia**.

6. Na skrócone karcie **Ogólne** pola w sekcji **Aktualizacja** są istotne, jeśli używasz naprawy w magazynie.

    - W polu **Stan cyklu życia odebranego składnika majątku** wybierz stan cyklu życia składnika majątku, że składniki majątku, które są wybrane w żądaniu konserwacji powinny być automatycznie aktualizowane po odebraniu do naprawy w magazynie.
    - W polu **Stan cyklu życia dostarczonego składnika majątku** wybierz stan cyklu życia, że składniki majątku, które są wybrane w żądaniu konserwacji, powinny być automatycznie aktualizowane po zwróceniu z naprawy.

Na poniższej ilustracji pokazano przykład strony **Modele cyklu życia żądania konserwacji**.

![Strona Modele cyklu życia żądania konserwacji](media/06-setup-for-requests.png)

---
title: Ręcznie utworzone zlecenia pracy
description: W tym temacie opisano ręczne tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875839"
---
# <a name="manually-created-work-orders"></a>Ręcznie utworzone zlecenia pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Można także ręcznie tworzyć zlecenia pracy na dwa sposoby:

- We **wszystkich zleceniach** lub **aktywnych zleceniach roboczych**  
- we **wszystkich żądań konserwacji** lub **aktywnych żądań konserwacji** albo **moich żądań konserwacji lokalizacji czynności konserwacyjnych**.  

## <a name="create-work-order"></a>Utwórz zlecenie pracy

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Kliknij przycisk **Nowe**.

3. W menu rozwijanym **Utwórz zlecenie pracy** wybierz typ zlecenia pracy.

4. Dodaj opis jeśli jest wymagany.

5. Umożliwia wybór środka trwałego dla zlecenia produkcyjnego oraz typu zadania konserwacji.

>[!NOTE]
>Po wybraniu nadrzędnego składnika majątku dwie lub trzy karty są dostępne: karta **Moje składniki majątku** zawiera składniki majątku związane z lokalizacjami czynności konserwacyjnych, do których możesz (pracownik, który jest zalogowany w systemie) zostać przydzielony (ustalane w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md)). Jeśli lokalizacje czynności konserwacyjnych nie są skonfigurowane dla konserwatora w formularzu [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md), karta **Moje składniki majątku** nie będzie widoczna. Karta **Aktywne składniki majątku** zawiera listę wszystkich składników majątku ze stanem cyklu życia zasobu „Aktywny”. Na karcie **Widok składników majątku** jest wyświetlany widok drzewa lokalizacji czynności konserwacyjnych i składników majątku zainstalowanych w tych lokalizacjach.

6. W razie potrzeby wybierz **Wariant typu zadania konserwacji** i **zawód**.

7. W razie potrzeby można zmienić poziom usługi zlecenia produkcyjnego w polu **poziomu usług**.

8. Wybierz oczekiwane daty rozpoczęcia i zakończenia w polach pokrewnych.

9. Kliknij przycisk **OK**, aby utworzyć nowe zlecenie pracy.

10. W razie potrzeby edytuj zlecenie produkcyjne we **wszystkichzleceniach roboczych**.

- We **wszystkich zleceniach pracy** do zlecenia produkcyjnego w widoku Szczegóły można dodać kilka środków trwałych, dodając wiersze w skróconej karcie **Zadania konserwacji zlecenia pracy**. Dla składnika moża wybrać tylko typy zadań konserwacji, które są związane z konfiguracją typu składnika majatku, który jest używany dla składnika majatku.  
- Jeśli zmieniłeś poziom obsługi zasobów lub krytyczność zasobu po użyciu ich w zleceniu pracy (odnieś się do [Poziomy usług składnika majątku](../setup-for-objects/object-priorities.md) [Krytyczności składników majątku](../setup-for-objects/object-criticalities.md)), poziom usługi lub krytyczność zlecenia pracy nie są odpowiednio aktualizowane.
- Krytyczność zlecenia pracy jest ponownie obliczana za każdym razem, gdy wiersz zlecenia pracy jest dodawany lub usuwany w zleceniu pracy.
- W **Wszystkie zlecenia pracy** widoku szczegółowym > widok **Nagłówek** > na skróconej karcie **Harmonogram** można wybrać grupę pracowników odpowiedzialnych za obsługę techniczną lub pracownika odpowiedzialnego za obsługę w polach **Grupa odpowiedzialna** lub **Osoba odpowiedzialna**. Te ustawienia można zmieniać, dopóki jest aktywne zlecenie produkcyjne, na przykład w przypadku zmiany stanu cyklu życia zamówienia pracy. Automatyczne wybieranie dokonane podczas tworzenia zlecenia produkcyjnego jest oparte na ustawieniach **odpowiedzialnych pracowników obsługi technicznej**. W przypadku dodawania lub usuwania zadań związanych z zamówieniami pracy po utworzeniu zlecenia produkcyjnego pole **Grupa odpowiedzialna** i **osoba odpowiedzialna** są puste po zaktualizowaniu zlecenia produkcyjnego formularz ustawień dla grupy pracowników odpowiedzialnej za konserwację lub odpowiedzialnego pracownika obsługi. Jeśli pole **grupy** lub **osoby** odpowiedzialnej jest już wypełnione podczas aktualizowania zlecenia produkcyjnego, nie są wprowadzane żadne zmiany. 

- W **Stan konserwacji** można obliczać uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.  

- W skróconej karcie **szczegółów wiersza** należy używać **pól szerokości geograficznej** i **długości geograficznej** w celu dodania współrzędnych geograficznych środka trwałego wybranego dla zadania zlecenia produkcyjnego.  

## <a name="create-related-work-order"></a>Utwórz powiązane zlecenie pracy

Można utworzyć powiązane zlecenie robocze z istniejącym zleceniem produkcyjnym, jeśli na przykład użytkownik chce pracować z głównymi i pomocniczymi zleceniami produkcyjnymi. Nowe zlecenie produkcyjne jest oparte na zadaniu zlecenia produkcyjnego z istniejącego zlecenia produkcyjnego.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie produkcyjne, dla którego chcesz wykonać powiązane zlecenie

3. Kliknij **Powiązane zlecenie pracy**.

4. W oknie rozwijanym **Utwórz pokrewne zlecenie pracy** wybierz zadanie zlecenia produkcyjnego, dla którego ma zostać utworzone powiązane zlecenie produkcyjne w **polu zadanie zlecenia pracy**.

5. Wybierz zadanie konserwacji, wpisz pole **typu zadania konserwacji** i w razie potrzeby pokrewny typ zadania związanego wariant i zawód w polach **Wariant typu zadania konserwacji** i **Zawód** .

6. Jeśli jest to pierwsze powiązane ze sobą zlecenie robocze, kliknij przycisk **Nowe zlecenie pracy**.

7. Wybierz **typ zlecenia pracy** i **opis** w odpowiednich polach.

8. W razie potrzeby można zmienić poziom usługi zlecenia pracy w polu **poziomu usług**.

9. Wpisz oczekiwane daty rozpoczęcia i zakończenia w polach pokrewnych.

10. Kliknij przycisk **OK**. Nowe powiązane zlecenie produkcyjne jest wyświetlane na liście **wszystkie zlecenia produkcyjne**.

11. W przypadku utworzenia powiązanego zlecenia produkcyjnego w zleceniu produkcyjnym, które ma już powiązane zlecenia, można dodać zadanie zlecenia produkcyjnego do już powiązanego zlecenia produkcyjnego. Aby to zrobić, należy kliknąć **Dodaj do powiązanego zlecenia pracy** przycisk w kroku 6. Następnie należy wybrać powiązane zlecenie produkcyjne, do którego ma zostać dodane nowe zadanie zlecenia produkcyjnego. W razie potrzeby edytuj pola **Poziom usług**, **Oczekiwana data rozpoczęcia** i **Oczekiwana data zakończenia** i kliknij **OK**. Zadanie zlecenia produkcyjnego jest dodawane do istniejącego powiązanego zlecenia pracy.


![Rysunek 1](media/03-work-orders.png)

**Uwaga:** w przypadku skonfigurowania powiązanej maski zleceń roboczych w polach **Parametry zarządzania składnikami majątku** > **Zlecenia pracy** złącze > **Maska powiązanego zlecenia pracy**, identyfikatory zleceń roboczych zostaną utworzone zgodnie z konfiguracją maski. Jeśli nie skonfigurowano powiązanej maski zlecenia produkcyjnego, dla pokrewnych zleceń produkcyjnych zostanie użyty kolejny dostępny identyfikator zlecenia pracy.

## <a name="copy-work-order"></a>Kopiuj zlecenie pracy

Istnieje możliwość szybkiego utworzenia nowego zlecenia produkcyjnego na podstawie istniejącego zlecenia produkcyjnego. Ta metoda pracy z zleceniami produkcyjnymi różni się od tworzenia zleceń roboczych na podstawie planów konserwacji. Jest to przydatne na przykład wtedy, gdy zlecenie produkcyjne zawiera wiele zadań zlecenia pracy z różnymi zadaniami dotyczącymi różnych środków trwałych, które powinny zostać wykonane w regularnych odstępach czasu.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Umożliwia wybranie zlecenia produkcyjnego, z którego ma zostać skopiowana zawartość.

3. Kliknij **Kopiuj zlecenie pracy**. Zostanie wyświetlona konfiguracja zlecenia produkcyjnego z wybranego zlecenia produkcyjnego. W razie potrzeby można edytować niektóre pola.

4. Kliknij **OK**, aby utworzyć nowe zlecenie pracy.

5. W razie potrzeby edytuj zlecenie produkcyjne we **wszystkichzleceniach roboczych**.

>[!NOTE]
>Po utworzeniu nowego zlecenia produkcyjnego niektóre informacje są kopiowane bezpośrednio z istniejącego zlecenia produkcyjnego. Informacje dotyczące prognoz, narzędzi, list kontrolnych obsługi, lokalizacji funkcjonalnej, adresów i planowania nie są kopiowane, ale zostały zainicjowane z bieżących ustawień modułu Zarządzanie środkami trwałymi. Oznacza to, że w przypadku wprowadzenia w nich zmian w czasie tworzenia pierwszego zlecenia produkcyjnego, zmiany te zostaną uwzględnione w nowo utworzonym zleceniu produkcyjnym. Przykłady to zmiany prognoz lub zaktualizowane listy kontrolne obsługi.


![Rysunek 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Tworzenie zlecenia pracy oparte na żądaniu konserwacji

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Żądania konserwacji** > **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.

2. Wybierz zadania konserwacyjne, dla których chcesz utworzyć zlecenie prac i kliknij pozycję **Edytuj**.

3. We **wszystkich żądaniach**kliknij przycisk **zlecenie pracy**.

4. Wprowadź listę rozwijaną **zlecenia pracy**. Jeśli w ramach zlecenia serwisowego wybrano typ zadania obsługi, można wybrać inny typ zadania obsługi, jeśli jest on wymagany podczas tworzenia zlecenia produkcyjnego.

5. Kliknij przycisk **OK**. Zostanie wyświetlony komunikat informujący o utworzeniu zlecenia produkcyjnego.

6. Aby sprawdzić, które zlecenia produkcyjne są połączone z **żądaniem obsługi, wybierz żądanie konserwacji na listach Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji** obsługi technicznej, a następnie kliknij przycisk **Zlecenia pracy**.


![Rysunek 3](media/05-work-orders.png)


>[!NOTE]
>Zlecenia produkcyjne mogą być również tworzone automatycznie przez planowanie zadań planu konserwacji lub przez skonfigurowanie w składniku aktywów opcji automatycznego tworzenia lub zaokrąglania konserwacji. Zlecenia produkcyjne utworzone na podstawie żądań obsługi w **harmonogramie konserwacji** są tworzone przy użyciu typów zadań konserwacji wybranych w ramach żądań obsługi.


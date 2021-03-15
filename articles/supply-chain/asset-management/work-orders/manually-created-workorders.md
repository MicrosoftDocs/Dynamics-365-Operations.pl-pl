---
title: Ręcznie utworzone zlecenia pracy
description: W tym temacie opisano ręczne tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8c787dbc9889139df76b9b102deb18fce567e382
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017875"
---
# <a name="manually-created-work-orders"></a>Ręcznie utworzone zlecenia pracy

[!include [banner](../../includes/banner.md)]


Można także ręcznie tworzyć zlecenia pracy na dwa sposoby:

- Na stronie **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy** 
- Na stronie **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji** lub **Moje żądania konserwacji lokalizacji czynności konserwacyjnych** 

## <a name="create-work-order"></a>Utwórz zlecenie pracy

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz pozycję **Nowy**.

3. W oknie dialogowym **Utwórz zlecenie pracy** wybierz zlecenie pracy w polu **Typ zlecenia pracy**.

4. Dodaj **Opis** jeśli jest wymagany.

5. W polu **Składnik majątku** wybierz składnik majątku.

>[!NOTE]
>Po wybraniu środka trwałego na liście rozwijanej **Składnik majątku** mogą być dostępne trzy karty: 

- **Aktywne składniki majątku** - ta karta zawiera listę wszystkich składników majątku ze stanem cyklu życia zasobu „Aktywny”. 
- **Widok składników majątku** - na tej karcie jest wyświetlany widok drzewa lokalizacji czynności konserwacyjnych i składników majątku zainstalowanych w tych lokalizacjach czynności konserwacyjnych.
- **Moje składniki majątku** - na tej karcie znajdują się składniki majątku powiązane z lokalizacjami czynności konserwacyjnych, do których może być przypisany pracownik zalogowany do systemu. (Aby uzyskać informacje dotyczące konfiguracji, należy zapoznać się z [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).) Jeśli dla pracownika nie jest skonfigurowana żadna lokalizacja czynności konserwacyjnych w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md), karta **Moje składniki majątku** jest niedostępna. 

6. W polu **Typ zadania konserwacji** wybierz typ zadania konserwacji dla zlecenia pracy.

7. W razie potrzeby wybierz **Wariant typu zadania konserwacji** i **zawód**.

8. W razie potrzeby można zmienić poziom usługi zlecenia produkcyjnego w polu **poziomu usług**.

9. Wybierz daty **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** w polach pokrewnych.

10. Kliknij **OK**, aby utworzyć zlecenie pracy.

11. Na stronie listy **Wszystkie zlecenia pracy** można edytować to zamówienie pracy w miarę potrzeb.

Należy uwzględnić następujące informacje:

- W widoku szczegółowym na stronie listy **Wszystkie zlecenia pracy** do zlecenia pracy można dodać kilka składników majątku, dodając wiersze na skróconej karcie **Zadania konserwacji zlecenia pracy**. Dla składnika moża wybrać tylko typy zadań konserwacji, które są określone w typie składnika majatku, który jest używany dla składnika majatku.  

- Jeśli zmienisz poziom usługi składnika majątku lub krytyczność składnika majątku po użyciu składnika majątku w zleceniu pracy, poziom usług lub krytyczność w zleceniu pracy nie zostanie odpowiednio zaktualizowany. Aby uzyskać więcej informacji o poziomach usług i ich krytyczności, zapoznaj się z tematem [Poziomy usług składnika majątku](../setup-for-objects/object-priorities.md) i [Typy krytyczności składnika majątku](../setup-for-objects/object-criticalities.md).

- Krytyczność na zleceniu pracy jest przeliczana za każdym razem, gdy wiersz zadania zlecenia pracy jest dodawany lub usuwany ze zlecenia pracy.

- W widoku szczegółowym **Wszystkie zlecenia pracy** > na karcie **Nagłówek** > na skróconej karcie **Harmonogram** w polach **Grupa odpowiedzialna** lub **Osoba odpowiedzialna** można wybrać grupę pracowników odpowiedzialnych za obsługę techniczną lub pracownika odpowiedzialnego za obsługę. Te ustawienia można zmienić, gdy jest aktywne zlecenie pracy. Można na przykład zmienić je po zmianie stanu cyklu życia zlecenia pracy. Automatyczne wybieranie dokonane podczas tworzenia zlecenia produkcyjnego jest oparte na ustawieniach na stronie **Odpowiedzialni konserwatorzy**. W przypadku dodawania lub usuwania zadań związanych z zamówieniami pracy po utworzeniu zlecenia pracy i jeśli pola **Grupa odpowiedzialna** i **Osoba odpowiedzialna** są puste po zaktualizowaniu zlecenia pracy, Zarządzanie składnikami majątku stara się znaleźć możliwie pasującą odpowiedzialną grupę konserwatorów lub odpowiedzialnego konserwatora na stronie ustawień. Jeśli pole **Grupa odpowiedzialna** lub **Osoba odpowiedzialna** jest już ustawione podczas aktualizowania zlecenia produkcyjnego, nie są wprowadzane żadne zmiany. Aby uzyskać więcej informacji na temat konfiguracji odpowiedzialnych konserwatorów i grup konserwatorów, zobacz temat [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).

- Na stronie [Stan konserwacji](../controlling-and-reporting/maintenance-status.md) można obliczać uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń pracy.  

- W widoku szczegółów strony **Wszystkie zlecenia pracy** na skróconej karcie **Szczegóły wiersza** można używać pól **Szerokość geograficzna** i **Długość geograficzna** w celu dodania współrzędnych geograficznych wybranego składnika majątku w zadaniu zlecenia pracy.  


## <a name="create-related-work-order"></a>Utwórz powiązane zlecenie pracy

Można utworzyć nowe zlecenie pracy odnoszące się do istniejącego zlecenia pracy. Jest to przydatne, jeśli użytkownik, na przykład, chce pracować z głównymi i pomocniczymi zleceniami pracy. Nowe zlecenie produkcyjne jest oparte na zadaniu zlecenia produkcyjnego z istniejącego zlecenia produkcyjnego.

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy, dla którego chcesz stworzyć powiązane zlecenie pracy.

3. W okienku akcji, na karcie **Zlecenie pracy**, w grupie **Nowe** wybierz **Powiązane zlecenie pracy**.

4. W oknie dialogowym **Utwórz pokrewne zlecenie pracy** w polu **Zadanie zlecenia pracy** wybierz zadanie zlecenia pracy, dla którego chcesz stworzyć powiązane zlecenie pracy.

5. W polu **Typ zadania konserwacji** wybierz typ zadania konserwacji.

6. W polach **Wariant typu zadania konserwacji** i **Zawód** wybierz wariant i zawód związany z typem zadania konserwacji według potrzeb.

7. Jeśli to zlecenie pracy jest pierwszym powiązanym zleceniem pracy, które zostało utworzone dla wybranego zlecenia pracy, wykonaj następujące kroki:
    1. Wybierz opcje **Nowe zlecenie pracy**.
    2. W  polu **Typ zlecenia pracy** wybierz typ zlecenia pracy.
    3. W polu **Opis** wprowadź opis.
    4. W polu **Poziom usług** w razie potrzeby można zmienić poziom usługi zlecenia pracy.
    5. W polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** wybierz oczekiwaną datę początkową i końcową.
    6. Kliknij przycisk **OK**. Nowe powiązane zlecenie produkcyjne jest wyświetlane na stronie listy **Wszystkie zlecenia pracy**.  

8. Jeśli zlecenie pracy tworzone w tym powiązanym zleceniu pracy dla już ma powiązane zlecenia pracy, należy wykonać następujące kroki w celu dodania nowego zadania zlecenia pracy do istniejącego powiązanego zlecenia pracy:
    1. Wybierz opcję **Dodaj do pokrewnego zlecenia pracy**.
    2. W polu **Zlecenie pracy** należy wybrać powiązane zlecenie pracy, do którego ma zostać dodane nowe zadanie zlecenia pracy.
    3. W polu **Poziom usług** w razie potrzeby można zmienić poziom usługi zlecenia pracy.
    4. W polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** zmień oczekiwaną datę początkową i końcową według potrzeby.
    5. Kliknij przycisk **OK**. Zadanie zlecenia produkcyjnego jest dodawane do istniejącego powiązanego zlecenia pracy.

Na poniższej ilustracji pokazano przykład okna dialogowego **Utwórz powiązane zlecenie pracy**.

![Rysunek 1](media/03-work-orders.png)

>[!NOTE]
>W przypadku skonfigurowania powiązanej maski zleceń pracy w polach **Parametry zarządzania składnikami majątku** > **karta Zlecenia pracy** > **Maska powiązanego zlecenia pracy**, identyfikatory zleceń pracy zostaną utworzone zgodnie z konfiguracją maski. Jeśli nie skonfigurowano powiązanej maski zlecenia pracy, dla pokrewnych zleceń pracy jest użyty kolejny dostępny identyfikator zlecenia pracy.

## <a name="copy-a-work-order"></a>Kopiuj zlecenie pracy

Istnieje możliwość szybkiego utworzenia nowego zlecenia pracy na podstawie istniejącego zlecenia pracy. Ta metoda pracy z zleceniami pracy różni się od tworzenia zleceń pracy na podstawie [planów konserwacji](../preventive-and-reactive-maintenance/maintenance-plans.md). Jest to przydatne na przykład wtedy, gdy zlecenie pracy zawiera wiele zadań zlecenia pracy z różnymi zadaniami dotyczącymi różnych składników majątku, które powinny zostać wykonane w regularnych odstępach czasu.

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Umożliwia wybranie zlecenia pracy, z którego ma zostać skopiowana zawartość.

3. W okienku akcji, na karcie > **Zlecenie pracy** > w grupie **Nowe** wybierz **Kopiuj zlecenie pracy**.

4. Zostanie wyświetlona konfiguracja zlecenia produkcyjnego z wybranego zlecenia produkcyjnego. W razie potrzeby można edytować niektóre pola.

5. Wybierz **OK**, aby utworzyć nowe zlecenie pracy.

6. Na stronie listy **Wszystkie zlecenia pracy** można edytować to zamówienie pracy w miarę potrzeb.

>[!NOTE]
>Po utworzeniu nowego zlecenia produkcyjnego niektóre informacje są kopiowane bezpośrednio z istniejącego zlecenia produkcyjnego. Nie są kopiowane informacje o prognozach, narzędziach, listach kontrolnych obsługi, lokalizacji czynności konserwacyjnych, adresach i planowaniu. Zamiast tego jest on inicjowany z poziomu bieżącej konfiguracji w module Zarządzanie składnikami majątku. Z tego względu, jeśli informacje te zostały zmienione między momentem utworzenia pierwszego zlecenia pracy a momentem dokonania kopii zlecenia, zmiany zostaną uwzględnione w nowym zleceniu pracy. Przykłady to między innymi zmiany prognoz lub aktualizacje list kontrolnych konserwowanego składnika majątku.

Na poniższej ilustracji przedstawiono przykład okna dialogowego **Kopiuj zlecenie pracy**.

![Rysunek 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Tworzenie zlecenia pracy oparte na żądaniu konserwacji

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Żądania konserwacji** > **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.

2. Wybierz żądanie konserwacyji, dla którego chcesz utworzyć zlecenie pracy i kliknij pozycję **Edytuj**.

3. W okienku akcji, na karcie > **Żądanie konserwacji** > w grupie **Nowe** wybierz **Zlecenie pracy**.

4. W oknie dialogowym **Zlecenie pracy** określ pola. Jeśli w ramach zlecenia serwisowego wybrano typ zadania obsługi, można wybrać inny typ zadania obsługi, jeśli jest on wymagany podczas tworzenia zlecenia produkcyjnego.

5. Kliknij przycisk **OK**. Komunikat powiadamia, że zlecenie pracy zostało utworzone.

6. Aby zobaczyć zlecenia pracy, które są połączone z żądaniem konserwacji, wybierz żądanie konserwacji na stronie list **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**. W okienku akcji, na karcie **Żądanie konserwacji** w grupie **Wyświetl** wybierz **Zlecenia pracy**.


Na poniższej ilustracji przedstawiono przykład okna dialogowego **Tworzenie zlecenia pracy**.

![Rysunek 3](media/05-work-orders.png)


>[!NOTE]
>Jeśli chcesz, żeby zlecenia pracy były tworzone automatycznie, możesz zaplanować zadania planu konserwacji lub ustawić „Automatyczne tworzenie” [planów konserwacji](../preventive-and-reactive-maintenance/maintenance-plans.md) lub [serii czynności konserwacyjnych](../preventive-and-reactive-maintenance/maintenance-rounds.md) dla składnika majątku. Zlecenia pracy utworzone na podstawie żądań konserwacji na stronie listy **Wszystkie harmonogramy konserwacji** mają typy zadań konserwacji, które są wybrane w żądaniach konserwacji.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
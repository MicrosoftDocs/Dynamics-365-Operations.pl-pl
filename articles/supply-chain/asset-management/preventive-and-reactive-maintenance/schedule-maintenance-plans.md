---
title: Planowanie planów konserwacji
description: W tym temacie wyjaśniono tworzenie planów konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9c19f999a94e6ad8451c208cf204d0b59306b77d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837808"
---
# <a name="schedule-maintenance-plans"></a>Planowanie planów konserwacji

[!include [banner](../../includes/banner.md)]

 

Planowanie planowania konserwacji powoduje generowanie wpisów kalendarza dla środków trwałych na podstawie planów eksploatacji ustawionych dla składników majątku. Wpisy kalendarza można planować na podstawie wybranych planów obsługi, typów składników majątku oraz składników majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Konserwacja zapobiegawcza** > **Planowanie planów konserwacji**.

2. Istnieje możliwość wybrania przedziału czasu w polach **Okres** i **częstotliwości okresu**.

>[!NOTE]
>Pola **Okres** i **Częstotliwość okresu** wskazują na to, jak długo mają być tworzone wiersze harmonogramu eksploatacji na podstawie utworzonych planów eksploatacji (opartych na czasie lub licznikach). Na poniższym rysunku wiersze harmonogramu konserwacji (= propozycje zleceń pracy) są tworzone od daty bieżącej i trzech miesięcy.

3. Wybierz wartość tak w polu **Automatyczne tworzenie, jeśli jest określone w wierszu**, jeśli zlecenia produkcyjne mają być automatycznie tworzone zgodnie z wierszem planu konserwacji

>[!NOTE]
>Jeśli ten przycisk przełącznika ma wartość tak, *a* pole wyboru **automatyczne tworzenie** jest również zaznaczone w wierszach planu konserwacji w **Plany konserwacji**, to zlecenia są tworzone na podstawie wierszy planu konserwacji, a zostaną również utworzone wiersze harmonogramu konserwacji ze stanem „utworzone zlecenie pracy” Jeśli zaznaczono tylko jedną opcję (**Automatyczne tworzenie, jeśli jest określone w wierszu** w przycisku przełączania wierszy w tym oknie dialogowym lub w polu **automatyczne tworzenie** w formularzu **plany konserwacji**), tworzone są tylko wiersze harmonogramu konserwacji stan „utworzone”. W takim przypadku zlecenia pracy nie są tworzone.

4. Istnieje możliwość generowania wpisów kalendarza na podstawie planów konserwacji (czas lub licznik), środków trwałych, typów środków, lokalizacji funkcjonalnych oraz typów lokalizacji funkcjonalnych. Kliknij przycisk **filtr** i wybierz opcje, jeśli jest to wymagane.

- Odnośnie planowania planów konserwacji w lokalizacjach czynności koserwacyjnych: w przypadku aktualizacji konfiguracji typów składników majątku, producentów i modeli planów konserwacji w **Wszystkie lokalizacje funkcjonalne** > **Plany konserwacji** karta skrócona, po zaplanowaniu planów konserwacji , istniejące wpisy harmonogramu konserwacji związane z tą lokalizacją czynności koserwacyjnych są automatycznie usuwane. Aby utworzyć nowe wpisy kalendarza, które odpowiadają zaktualizowaniu ustawień planu konserwacji w lokalizacji czynności konserwacyjnych, należy uruchomić nowy harmonogram planu konserwacji dla tej lokalizacji czynności konserwacyjnych. Aby uzyskać więcej informacji na temat konfiguracji typów składników, producentów i modeli w lokalizacjach funkcjonalnych, należy zapoznać się z tematem [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md).

>*Przykład:* użytkownik chce utworzyć plan konserwacji dla określonej lokalizacji czynności konserwacyjnych, co oznacza, że podczas planowania planowania konserwacji zostaną uwzględnione wszystkie składniki majątku skonfigurowane w danej lokalizacji czynności konserwacji w danym momencie. W takim przypadku należy utworzyć plan konserwacji i wybrać określoną lokalizację czynności konserwacyjnych, ale nie należy dodawać żadnych składników majatku do planu konserwacji. W wyniku tego, podczas planowania tego planu konserwacji, wiersze harmonogramu konserwacji zostaną utworzone dla wszystkich składników majątku związanych z lokalizacją czynności konserwacyjnych o tej godzinie.

- W przypadku zmiany typów aktywów, producentów i modeli w **Typy składników majątku** zmiany te dotyczą tylko nowych składników majątku, w których jest używany zaktualizowany typ składników majątku. Przeczytaj więcej na temat ustawień typu składnika majątku w [Typy składników majątku](../setup-for-objects/object-types.md).  

5. Kliknij **OK**, aby rozpocząć generowanie wpisów harmonogramu konserwacji dla składników majątku. Wygenerowane wpisy zostaną wyświetlone na stronie listy **Wszystkie harmonogramy konserwacji**. Na poniższej ilustracji pokazano przykład okienka dialogowego **Szczegóły żądania konserwacji**.

![Rysunek 1](media/09-preventive-maintenance.png)

- Okno dialogowe **Planowanie planów konserwacji** umożliwia skonfigurowanie zadań wsadowych w skróconej karcie **Uruchom w tle** w celu automatycznego generowania wpisów kalendarza w regularnych odstępach czasu.  
- W przypadku planowania obsługi, wiersze harmonogramu konserwacji z oczekiwaną datą rozpoczęcia i godziną wcześniejszą od daty i godziny systemowej nie zostaną utworzone.  

Poniższy rysunek przedstawia graficzną ilustrację obliczania planu konserwacji opartego na czasie.  

![Rysunek 2](media/10-preventive-maintenance.jpg)

W odniesieniu do planów obsługi opartych na licznikach: w poniższej liczbie pokazano dwa różne cykle rejestracji liczników. Są one oparte na planie obsługi, ustawionym dla środka trwałego „V0001”, spodziewając się, że środek trwały (samochód) ma się rozpocząć w przybliżeniu 2 000 km co miesiąc.

W pierwszym przykładzie oczekiwano 2 000 km, co miesiąc. Zgodnie z planem konserwacji opartej na licznikach, próg wynosi 2 000 km, co oznacza, że po uruchomieniu planowania planu konserwacji wiersz harmonogramu konserwacji powinien zostać utworzony za każdym razem, gdy zostanie osiągnięty próg 2 000 kilometra. W przykładzie 1 Istnieją 4 wiersze rejestracji, ale próg 2 000 kilometra został tylko raz osiągnięty. Oznacza to, że po uruchomieniu planów konserwacji dla tego składnika aktywów, na przykład przez 3-miesięczny okres, zostanie utworzony tylko jeden wiersz harmonogramu konserwacji.

Na następnej ilustracji co miesiąc rejestruje się co najmniej 2 000 km. W związku z tym zostaną utworzone trzy wiersze obsługi, jeśli plan konserwacji dla danego składnika majątku jest planowany w okresie 3 miesięcy. 

Przedstawione tu przykłady pokazują, że wszystkie rejestracje liczników wykonane na składniku majatku pokazują trend z opisem zużycia i rozpiętości składnika. Ta trend jest używany jako podstawa obliczeń czasu planowania planów konserwacji.

![Rysunek 3](media/11-preventive-maintenance.png)

![Rysunek 4](media/12-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
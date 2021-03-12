---
title: Odroczone przetwarzanie pracy magazynowej
description: W tym temacie opisano funkcje, która udostępnia odroczone przetwarzanie operacji odłożenia pracy magazynowej w usłudze Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c85dd895e18805da2d1daf5f90f64db82bdc0116
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973792"
---
# <a name="deferred-processing-of-warehouse-work"></a>Odroczone przetwarzanie pracy magazynowej

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, która udostępnia odroczone przetwarzanie operacji odłożenia pracy magazynowej w programie Dynamics 365 Supply Chain Management.

Funkcja odroczonego przetwarzania umożliwia pracownikom magazynu kontynuowanie innych prac podczas przetwarzania operacji odłożenia w tle. Odroczonego przetwarzania jest przydatne, gdy wiele wierszy pracy musi być przetwarzanych i pracownik może pozwolić, aby praca była przetwarzana asynchronicznie. Jest to również przydatne, kiedy na serwer zdarzają się nieplanowane wydłużenia czasu przetwarzania, a zwiększony czas przetwarzania może wpłynąć na produktywność użytkownika.

Przetwarzanie w tle uzyskuje się za pomocą struktury SysOperation. Aby uzyskać więcej informacji, zobacz temat [Omówienie struktury SysOperation](https://docs.microsoft.com/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Konfigurowanie zasad przetwarzania pracy

Aby użyć odroczonego przetwarzania, należy skonfigurować zasady przetwarzania pracy i używać ich.

Zasady konfiguruje się na stronie **Zasady przetwarzania pracy**. W poniższej tabeli opisano pola znajdujące się na tej stronie.

| Pole                           | Opis |
|---------------------------------|-------------|
| Nazwa zasady przetwarzania pracy     | Nazwa zasady przetwarzania pracy. |
| Typ zlecenia                 | Typ zlecenia pracy, do którego zastosowano zasadę. |
| Operacja                       | Operacja, która jest przetwarzana przy użyciu zasad. |
| Metoda przetwarzania pracy          | Metoda wolumetryczna używana do przetwarzania wiersza pracy. Jeśli metoda jest ustawiona na **Natychmiastowe**, zachowanie przypomina zachowanie, gdy żadne zasady przetwarzania pracy nie są używane do przetworzenia wiersza. Jeśli metoda jest ustawiona na **Odroczone**, używane jest odroczone przetwarzania, które używa struktury partii. |
| Próg odroczonego przetwarzania   | Wartość **0** (zero) wskazuje, że nie istnieje żaden próg. W takim przypadku używane jest odroczone przetwarzanie, o ile jest to możliwe. Jeśli wynik obliczenia konkretnego progu jest poniżej progu, używana jest metoda Natychmiastowe. W przeciwnym razie używana jest metoda Odroczona, o ile jest to możliwe. W przypadku pracy związanej ze sprzedażą i przenoszeniem próg jest obliczany jako liczba skojarzonych źródłowych wierszy obciążenia, które są przetwarzane w odniesieniu do pracy. W odniesieniu do pracy uzupełniania, próg jest obliczany jako liczba wierszy pracy, które są uzupełniane przez pracę. Ustawiając próg, na przykład **5** dla sprzedaży, mniejszych prac, które mają mniej niż pięć wierszy początkowego obciążenia źródła, nie będzie używane przetwarzanie odroczonego, ale w przypadku większych prac będzie ono używane. Próg ma zastosowane tylko wtedy, gdy metoda przetwarzania pracy jest ustawiona na **Odroczone**. |
| Grupa przetwarzania wsadowego odroczonego przetwarzania |Grupa przetwarzania wsadowego używana do przetwarzania. |

W przypadku odroczonego przetwarzania odłożenia obsługiwane są następujące typy zleceń pracy: zamówienie sprzedaży, wydanie zamówienia przeniesienia i uzupełnienie zapasów.

## <a name="assigning-the-work-creation-policy"></a>Przypisywanie zasad tworzenia pracy

Zasady tworzenia pracy można przypisywać w parametrach zarządzania magazynem. Można je przypisywać również na poziomie poszczególnych magazynów. Jeśli zasada jest przypisana do magazynu, jest stosowana tylko do pracy utworzonej dla tego magazynu. Jeśli na poziomie magazynu nie przypisano żadnej zasady, stosowana jest zasada z parametrów zarządzania magazynem.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Wyświetlanie zadań odroczonego przetwarzania odłożenia

Zadania odroczonego przetwarzania odłożenia można wyświetlić na stronie **Zadania odroczonego przetwarzania odłożenia**.

Domyślnie wyświetlane są zadania **Ukończone**.

| Pole            | Opis |
|------------------|-------------|
| Stan           | Stan zadania. |
| Stan zadania wsadowego | Stan powiązanego zadania wsadowego. Jeśli zadanie wsadowe zostało przetworzone, historia partii zawiera dziennik i informacje z zadania wsadowego. |

Poniżej znajduje się wyjaśnienie możliwych statusów:

- **Oczekiwanie** — powiązane zadanie wsadowe oczekuje na przetwarzanie na serwerze wsadowym.
- **Niepowodzenie** — przetwarzanie nie powiodło się. Zadanie może być ponownie przetwarzane przy użyciu akcji **Przetwarzaj odroczone odłożenie** lub może zostać anulowane za pomocą akcji **Anuluj odroczone odłożenie**.
- **Ukończono** — zadanie zostało ukończone.

## <a name="impact-on-closed-work-dates"></a>Wpływ na zamknięte daty pracy

Gdy używane jest odroczone przetwarzanie odłożenia, data zamknięcia pracy jest ustawiona jak data/godzina utworzona zadań przetwarzania odroczonego odłożenia. Data zamknięcia pracy jest używana, ponieważ jest to najlepsze oszacowanie, kiedy operacja odłożenia została zakończona.

## <a name="reprocessing-a-failed-task"></a>Ponowne przetwarzanie nieudanego zadania

Można ponownie przetworzyć zadania, które się nie powiodło, zaznaczając go na stronie, a następnie wybierając **Przetwarzaj odroczone odłożenie**. Ponowne przetwarzanie odpowiada sytuacji, gdy użytkownik zakończy odłożenia z urządzenia przenośnego tak, jakby został ustawiony do natychmiastowego przetworzenia.

## <a name="canceling-failed-tasks"></a>Anulowanie nieudanych zadań

Anulować można tylko nieudane zadania. Po anulowaniu zadania można je przypisać do nowego użytkownika. Alternatywnie zadanie może pozostać przypisane do użytkownika, który przetworzył pracę. Anulowanie odpowiada sytuacji, w której praca jest przywracana do urządzenia przenośnego tak, jakby ostatni krok odebrania został właśnie zakończony i praca wymaga odłożenia. Użytkownik będzie mógł jednak określić, że praca jest „inna”, ponieważ będzie miała tylko krok odłożenia, a lokalizacja będzie odpowiadać lokalizacji przypisanej użytkownikowi, który przetworzył prace, jako finalna lokalizacja odłożenia.

Gdy zadanie jest anulowane, praca nie jest już zablokowana przez przyczyną zablokowania przetwarzania odłożenia. Może być ponownie przetworzona za pomocą urządzenia przenośnego.

Rekord zadania jest usuwany po anulowaniu zadania.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Konfigurowanie menu urządzenia przenośnego w celu pominięcia zasady odroczonego przetwarzania

Można skonfigurować element menu urządzenia przenośnego, tak aby zasady przetwarzania odroczonego nie były używane. Praca jest następnie przetwarzana bez używania zasady odroczonego przetwarzania. Ta funkcja umożliwia przełożonemu użycie określonego elementu menu, kiedy odroczone odłożenie nie jest używane. Aby go skonfigurować, ustaw pole **Zasada odroczonego przetwarzania odłożenia** na **Zastąp ustawienia i jednocześnie przetwórz proces odłożenia**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Ograniczenia, kiedy odroczenie przetwarzania odłożenia nie jest stosowane

Istnieje kilka scenariuszy, w których odroczenie przetwarzanie odłożenia nie jest stosowana, nawet jeśli zasada jest skonfigurowana. Oto kilka przykładów:

- Używane jest ręczne kończenie pracy.
- Praca jest kończona z użyciem automatycznego uzupełniania.
- Używane są szablony inspekcji.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Monitorowanie zadań odroczonego przetwarzania z obszaru roboczego Monitorowanie pracy wychodzącej

Obszar roboczy **Monitorowanie pracy wychodzącej** ma dwa kafelki ułatwiające monitorowanie odroczonych zadań przetwarzania odłożenia:

- **Nieudane odroczone zadania przetwarzania odłożenia** – ten kafelek pokazuje liczbę nieudanych zadań. Jeśli występują zadania, które się nie powiodły, menedżer magazynu musi je ponownie przetworzyć lub anulować, ponieważ nie będą one ponownie przetwarzane automatycznie.
- **Oczekujące odroczone zadania przetwarzania odłożenia** — ten kafelek pokazuje liczbę zadań, które miały stan **Oczekujące** przez ponad 10 minut. Jeśli kafelek zawiera liczbę, może to oznaczać, że wystąpił problem podczas przetwarzania wsadowego. Można ręcznie przetwarzać zadania **Oczekujące**. Jeśli zadanie wsadowe dla zadania jest przetwarzane później, po prostu nie powiedzie się, ponieważ będzie już przetworzone. Nie będzie żadnego wpływu.

## <a name="deleting-completed-tasks"></a>Usuwanie wykonanych zadań

Można usunąć odroczone zadania przetwarzania odłożenia, które zostały zakończone, zaznaczając je i usuwając je na stronie.

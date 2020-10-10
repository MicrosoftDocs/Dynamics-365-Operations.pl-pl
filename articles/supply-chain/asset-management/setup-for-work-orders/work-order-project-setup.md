---
title: Ustawienia projektu zlecenia pracy
description: W tym temacie opisano ustawienia projektu zlecenia pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a51837275203dc2d4f31dc4dec9bf970a7ebeba7
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889321"
---
# <a name="work-order-project-setup"></a>Ustawienia projektu zlecenia pracy

[!include [banner](../../includes/banner.md)]

 

W module **Zarządzanie składnikami majątku** dla każdego zadania zlecenia pracy jest wymagana relacja projektu Projekt skojarzony z zadaniem zlecenia pracy umożliwia śledzenie kosztów w różnych projektach związanych z zarządzaniem składnikami, takimi jak wewnętrzne projekty obsługi, projekty zarządzania serwisem i projekty inwestycyjne. 

## <a name="project-setup-for-a-work-order-job"></a>Ustawienia projektu zadania zlecenia pracy

Podczas tworzenia zadania zlecenia pracy w zleceniu pracy, ustawienia projektu w module **Zarządzanie projektami i ich księgowanie** oraz konfiguracja projektu zlecenia pracy w module **Zarządzanie składnikami majątku** decydują o tym, w jaki sposób można używać projektów do kontroli kosztu składnika majątku wybranegow tym zadaniu zlecenia pracy. W tej sekcji opisano następujące części ustawień projektu, które są używane dla zlecenia pracy: projekt nadrzędny (identyfikator projektu), typ projektu, działania projektowe i wymiary finansowe:

- Podczas tworzenia zadania zlecenia pracy w zleceniu pracy automatycznie tworzone są unikatowe identyfikatory projektów i powiązane działania projektu. Jeśli jednak kilka zadań zlecenia pracy w zleceniu pracy zawiera ten sam składnik majątku, dla tych zleceń jest używany ten sam identyfikator projektu. Inaczej mówiąc, dla każdego składnika majątku w zleceniu pracy tworzony jest jeden identyfikator projektu.

    - Projekt nadrzędny (identyfikator projektu) zadania zlecenia jest znaleziony w konfiguracji projektu nadrzędnego. (Aby uzyskać więcej informacji o ustawieniach projektu nadrzędnego, zapoznaj się z następną sekcją) Jeśli na przykład klient lub lokalizacja czynności konserwacyjnych są kojarzone z określonym projektem nadrzędnym, projekt nadrzędny jest używany za każdym razem, gdy tworzone są zlecenia pracy dla tego odbiorcy lub tej lokalizacji czynności konserwacyjnych. Jeśli określony identyfikator projektu nie jest powiązany z określonym obiektem, na przykład z lokalizacją czynności konserwacyjnych, używany jest następny odpowiedni projekt nadrzędny w ustawieniach projektu zlecenia pracy.
    - Typ projektu jest wymagany dla każdego identyfikatora projektu. Typ projektu można znaleźć w ustawieniach grupy projektów. (Aby uzyskać więcej informacji o ustawieniach grupy projektów, zapoznaj się z następną sekcją) Jeśli w ustawieniach grupy projektów nie zostanie znaleziony odpowiednik, zostanie użyta Konfiguracja grupy projektów w projekcie nadrzędnym.
    - Konfiguracja wymagania działań projektu w prognozach i arkuszach jest kopiowana z projektu nadrzędnego do projektu zlecenia pracy. Jeśli opcje **godziny**, **wydatki** i **towar** mają wartość **tak** dla projektu, który jest używany jako projekt nadrzędny, działanie projektu jest obowiązkowe w prognozach i arkuszach. (Aby uzyskać dostęp do tych opcji **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**, a następnie wybierz projekt, który jest używany jako projekt nadrzędny. Opcje te znajdują się w sekcji **wymagania dotyczące działań w arkuszach** w skróconej karcie **Ustawienia**.)

- Wymiary finansowe są kopiowane ze składnika majątku i scalane z projektem nadrzędnym.

W następnej sekcji opisano sposób konfigurowania projektów nadrzędnych i grup projektów. Projekt nadrzędny i grupy nadrzędne służą do sterowania zleceniami pracy. Służą one także do tworzenia raportów o zleceniach pracy.

## <a name="set-up-work-order-projects"></a>Ustaw projekt zlecenia pracy

Przed rozpoczęciem tworzenia zleceń pracy należy skonfigurować projekty zleceń. Strona **Ustawienia projektu zlecenia pracy** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zlecenia pracy** \> **Ustawienia projektu**) zawiera dwie karty: **Projekt nadrzędny** i **Grupa projektów**.

Na karcie **projekt nadrzędny** można skonfigurować relacje projektu, które mogą być używane, jeśli żaden projekt nie jest skonfigurowany dla składnika majątku wybranego w zadaniu zlecenia pracy. Konfiguracja projektu nadrzędnego nie jest wymagana, jeśli firma używa projektów składników majątku. Jest to istotne tylko wtedy, gdy zamiast projektów składników majątku mają być używane projekty zleceń pracy. W takim przypadku należy skonfigurować co najmniej jeden projekt nadrzędny.

Na karcie **Grupa projektów** pmożna skonfigurować grupy projektów, które można kojarzyć z typami zleceń pracy, typami składników majątku i składnikami majątku.

Za pomocą grup projektów można tworzyć określone kategorie (grupy) używane do kontroli kosztów. Na przykład tworząc grupy projektów dla określonego typu składników majątku lub typów zleceń pracy, można szczegółowo śledzić koszty eksploatacji według typu.

Grupy projektów nie są wymagane. Jeśli nie zostaną skonfigurowane grupy projektów, projekt nadrzędny jest używany do określania grupy projektów i tworzony jest projekt podrzędny z grupy projektów projektu nadrzędnego.

Konfiguracja pozwala na pełną integrację z modułem **Zarządzanie projektami i ich księgowanie**. Dzięki temu można śledzić koszty związane z zleceniami pracy w powiązanych projektach. Poniższa procedura opisuje ustawienia projektów zleceń pracy.

1. Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Ustawienia projektu**.
2. Na karcie **Projekt nadrzędny** wybierz przycisk **Dodaj**.
3. W polach **Typ zlecenia pracy**, **Lokalizacja czynności konserwacyjnych**, **Typ składnika majątku** i **Składnik majątku** wybierz wymagane wartości. Dla każdego dodawanego wiersza można określić tylko jedno pole lub kilka pól. Liczba ustawionych pól określa kombinację, która jest używana w przypadku wybrania identyfikatora projektu w module Zarządzanie składnikami majątku. 

    W przypadku wybrania lokalizacji czynności konserwacyjnych zostaną automatycznie uwzględnione powiązane lokalizacje podrzędne. W przypadku wybrania składnika majątku można utworzyć więcej wierszy ustawień projektu zlecenia pracy dla tego samego składnika, ale można wybrać różne projekty dla tego składnika.

4. W polu **Identyfikator projektu** wybierz projekt, który ma być powiązany z konfiguracją utworzoną w kroku 3.
5. Jeśli ustawienia projektu powinny być ważne tylko dla określonego okresu, wybierz datę końcową w polu **Data zakończenia**. W przeciwnym razie należy zaznaczyć pole **Brak**.

    Domyślnie datą rozpoczęcia jest data, kiedy do strony zostanie dodany projekt zlecenia pracy. Jest on sterowany przez pole **Ważne od**, które jest domyślnie ukryte. Aby wyświetlić pole **Ważne od**, wybierz opcję **Wyświetl** \> **Wszystko**. Następnie można używać pola **Ważne od** w połączeniu z polem **Data zakończenia** w celu skonfigurowania ograniczonego okresu ważności dla projektu zlecenia pracy.

    ![Strona ustawień projektu zleceń pracy](media/17-setup-for-work-orders.png)

6. Na karcie **Grupa projektów** wybierz przycisk **Dodaj**.
7. W polu **Typ zlecenia pracy** wybierz typ zlecenia pracy.
8. Jeśli skojarzenie grupy projektów ma być bardziej szczegółowe, należy wybrać typ składnika majątku w polu **Typ składnika majątku** lub w polu **Składnik majątku**.
9. W polu **Grupa projektów** wybierz grupę projektów, która powinna być związana z typem zlecenia pracy. Na przykład typ zlecenia pracy o nazwie **Konserwacja zapobiegawcza** może być skojarzony z grupą projektów o nazwie **Kons. zap.** lub **Wewnętrzne**. Alternatywnie, typ **Inwestycja** zlecenia pracy używany dla zleceń pracy związanych z inwestycjami i środkami trwałymi może być skojarzony z grupą projektów o nazwie **Inwestowanie** lub **Inwestycje**.
10. Wybierz opcję **Zapisz**.

![Strona Ustawienia projektu zleceń pracy, Dodaj zlecenie pracy](media/18-setup-for-work-orders.png)

> [!NOTE]
> Podczas tworzenia wiersza zlecenia pracy, Zarządzanie składnikami majątku wyszukuje grupę projektów, która powinna być związana z projektem zadania zlecenia pracy. Wyszukiwanie jest oparte na konfiguracji opisanej w tym temacie. Każda grupa projektów ma powiązany Typ projektu. Grupy projektów, które mają typ **Czas i materiały** lub **Stała cena** są ważne tylko dla składników majątku związanych z kontem odbiorcy.
>
> W przypadku projektów nadrzędnych i grup projektów, gdy system wybiera dostępny projekt zlecenia pracy lub grupę projektów, wybór jest oparty na rekordach utworzonych za pomocą poprzedniej procedury. Zarządzanie składnikami majątku przechodzi między rekordami związanymi z projektem zlecenia pracy w celu sprawdzenia, czy jest możliwe jego dopasowanie. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, dla nadrzędnego projektu zlecenia pracy moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Składnik majatku**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Typ składnika majątku**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Lokalizacja czynności konserwacyjnych** itd. Jak widać w układzie strony **Ustawienia projektu zlecenia pracy** to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania. Jeśli nie zostanie znaleziony żaden odpowiednik, używany jest rekord domyślny, w którym jest wybrany tylko identyfikator projektu. Proces wyszukiwania powiązanej grupy projektów jest podobny. Zarządzanie składnikami majątku najpierw sprawdza, czy istnieje możliwe dopasowanie do pola **Składnik majątku**, a następnie dla pola **Typ składnika majątku**, a następnie dla pola **Typ zlecenia pracy**. Jeśli nie zostanie znaleziony żaden odpowiednik, używany jest rekord domyślny, w którym jest wybrany tylko grupa projektu.

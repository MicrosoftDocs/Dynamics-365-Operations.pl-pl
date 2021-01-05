---
title: Korekty limitu kredytu
description: W tym temacie opisano sposób konfigurowania i dodawania korekt limitu kredytu.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: d55a7c5e24213f70a1b71f89691f0e5be8c36f10
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446766"
---
# <a name="credit-limit-adjustments"></a>Korekty limitu kredytu 

[!include [banner](../includes/banner.md)]

Korekty limitu kredytu umożliwiają menedżerom kredytów aktualizowanie limitów kredytu i dat wygaśnięcia jednego odbiorcy, grupy odbiorców lub wszystkich odbiorców w procesie księgowania. Można dodawać wpisy korekty limitu kredytu, aby aktualizować grupy kredytowe odbiorców i odbiorców albo można je stosować do obliczania automatycznych limitów kredytowych. Zapisy mogą być następnie przeglądane, wysyłane do zatwierdzenia za pomocą przepływu pracy i księgowane na kontach odbiorców.

## <a name="set-up-credit-limit-adjustments"></a>Konfiguracja limitu kredytu odbiorcy

Istnieje możliwość tworzenia wpisów w arkuszu korekt limitu kredytu na stronie **Korekta limitu kredytu** (**Zarządzanie kredytem \> Korekta limitu kredytu \> Korekty limitu kredytu**).

1. Wybierz pozycję **Nowy**. Zostanie utworzona nowa grupa wpisów z numerem korekty limitu kredytu.
2. Umożliwia wybór typu korekty limitu kredytu:

    - Wybierz opcję **Limit kredytu**, aby zmienić limit kredytu odbiorcy.
    - Wybierz opcję **Tymczasowy limit kredytu**, aby utworzyć tymczasowy limit kredytu zamiast zmieniać bieżący limit kredytu odbiorcy. Tymczasowe limity kredytowe zastępują limit kredytu odbiorcy dla zdefiniowanego okresu. Po zakończeniu tego okresu ponownie zostanie użyty limit kredytu odbiorcy.
3. Wprowadź opis. 

Jeśli zaznaczono pole wyboru **Zaksięgowane**, zostały zastosowane limity kredytowe. Pole **Stan zatwierdzenia** wskazuje stan przepływu pracy w arkuszu. Przepływ pracy jest opcjonalny.

### <a name="add-credit-limit-adjustments"></a>Dodawanie limitu kredytu odbiorcy

Aby ręcznie dodać korekty limitu kredytu, zaznacz **Wiersze**, a następnie wykonaj następujące kroki.

1. Aby dodać korektę limitu kredytu dla odbiorcy, należy skorzystać z menu **Korekty odbiorcy**. Aby dodać limit kredytu dla grupy kredytu odbiorcy, należy wybrać **Korekty grupy kredytowej dla odbiorcy**.
2. Umożliwia wprowadzenie konta odbiorcy faktury dla konta odbiorcy faktury, które powinno zostać zaktualizowane przy użyciu nowego limitu kredytowego. Jeśli w kroku 1 wybrano **Korekty grupy kredyt odbiorcy**, należy wprowadzić grupę kredytową odbiorcy. W tym samym wierszu arkusza nie można wprowadzić konta odbiorcy i identyfikatora grupy kredytowej dla odbiorcy.

    Wyświetlany jest bieżący limit kredytu, a jego nazwa jest wyświetlana automatycznie.

3. Umożliwia wprowadzenie nowego limitu kredytowego, który powinien zastąpić bieżący limit kredytu podczas księgowania wpisu limitu kredytu.
4. Umożliwia wprowadzenie daty w celu zdefiniowania nowej daty ważności limitu kredytowego odbiorcy. Podczas tworzenia korekty limitu kredytu należy wprowadzić datę ważności limitu kredytowego.

Pole **Stan zatwierdzenia** wskazuje stan przepływu pracy w wierszu arkusza.

Jeśli korekty limitu kredytu mają być generowane automatycznie, można użyć menu **Generuj** w okienku akcji.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Dodawanie tymczasowego limitu kredytu odbiorcy

Aby ręcznie dodać tymczasowe korekty limitu kredytu, wykonaj następujące kroki dla wierszy arkusza.

1. Aby dodać korektę limitu kredytu dla odbiorcy, należy skorzystać z menu **Korekty odbiorcy**. Aby dodać limit kredytu dla grupy kredytu odbiorcy, należy wybrać **Korekty grupy kredytowej dla odbiorcy**.
2. Umożliwia wprowadzenie konta odbiorcy faktury dla konta odbiorcy faktury, które powinno zostać zaktualizowane przy użyciu nowego limitu kredytowego. Jeśli w kroku 1 wybrano **Korekty grupy kredyt odbiorcy**, należy wprowadzić grupę kredytową odbiorcy. W tym samym wierszu arkusza nie można wprowadzić konta odbiorcy i identyfikatora grupy kredytowej dla odbiorcy.

    Jeśli istnieje już aktywny lub przyszły tymczasowy limit kredytu, bieżący tymczasowy limit kredytu i zakres dat są wyświetlane dla każdego tymczasowego limitu kredytu. Nazwa zostanie wyświetlona automatycznie.

3. Umożliwia wprowadzenie nowego limitu kredytowego, który powinien zastąpić bieżący limit kredytu.
4. W polach **Nowe od daty** i **Nowe do daty** dnia zdefiniuj okres, po upływie którego obowiązuje zaawansowany limit kredytu. Podczas tworzenia korekty arkusza limitu kredytu należy wprowadzić daty ważności limitu kredytowego.

Pole **Stan zatwierdzenia** wskazuje stan przepływu pracy w wierszu arkusza.

## <a name="generate-credit-limit-adjustments"></a>Generuj limit kredytu odbiorcy

Można również automatycznie korygować limity kredytu. W okienku akcji wybierz **Generuj**, a następnie wybierz jedną z następujących opcji:

- Od istniejącego konta odbiorcy
- Z istniejącej grupy kredytu odbiorcy
- Automatyczne limity kredytu

### <a name="from-existing-customer"></a>Od istniejącego konta odbiorcy

Wiersze arkusza można tworzyć na podstawie istniejących odbiorców. Po wybraniu **Generuj \> Na podstawie istniejącego odbiorcy** wyświetlane jest okno dialogowe, w którym można podać kryteria wyboru odbiorców i obliczania nowych limitów.

1. Umożliwia wprowadzenie wartości korekty w celu dodania lub odjęcia kwoty z limitu kredytu. Wprowadź wartość ujemną, aby zmniejszyć bieżący limit kredytu lub wartość dodatnią, aby ją zwiększyć.
2. W polu **Typ wartości** wybierz sposób, w jaki wartość wprowadzona w kroku 1. powinna być używana do obliczania nowego limitu kredytu:

    - Wybierz opcję **Stała wartość**, aby zmienić limit kredytu o kwotę.
    - Wybierz opcję **Stała wartość**, aby zmienić limit kredytu o kwotę.

3. Umożliwia wprowadzenie wartości używanej do zaokrąglania obliczonego limitu kredytowego. Na przykład wprowadź **10,00**, aby zaokrąglić limit kredytu do najbliższej 10,00 jednostki waluty.
4. Ustaw pole **Metoda zaokrąglenia**, aby określić, czy reszta ma być zaokrąglana w górę czy w dół.
5. Pozwala wybrać metodę używaną do dostosowywania dat.

    - W przypadku wybraniawartości **Bezwzględnych** można wprowadzić daty definiujące zakres dat dla limitów kredytowych.
    - W przypadku wybrania opcji **Względnych** można wprowadzić daty przeciwstawne dla zakresu. Bieżący zakres dat dla limitu kredytu zostanie skorygowany o przesunięcie.

6. Użyj skróconej karty **Rekordy do uwzględniania** w celu filtrowania listy uwzględnionych odbiorców. Jeśli nie zostaną uwzględnione filtry, dla wszystkich odbiorców zostaną wygenerowane wpisy limitu kredytu.
7. Wybierz przycisk **OK**, aby utworzyć wpisy korekty limitu kredytu.

### <a name="from-existing-customer-credit-group"></a>Z istniejącej grupy kredytu odbiorcy

Wiersze arkusza można tworzyć na podstawie istniejących grup odbiorców kredytu. Po wybraniu **Generuj \> Na podstawie istniejącej grupy odbiorców kredytu** wyświetlane jest okno dialogowe, w którym można podać kryteria wyboru grup odbiorców kredytu i obliczania nowych limitów. Kryteria te są tymi samymi kryteriami, które są używane do tworzenia wierszy arkusza od istniejących odbiorców. Sprawdź kroki opisane w poprzedniej sekcji.

### <a name="automatic-credit-limits"></a>Automatyczne limity kredytu

Istnieje możliwość tworzenia automatycznych limitów kredytu w celu zdefiniowania i zaktualizowania limitów kredytowych odbiorców. Automatyczne limity kredytu są tworzone dla grupy ryzyka i są oparte na określonych wartościach, które są używane w grupach oceniających. Aby wygenerować wpisy limitu kredytu, można skorzystać z tych automatycznych limitów kredytu. Jeśli odbiorca został przypisany do określonej grupy ryzyka, a informacje kredytowe odbiorcy odpowiadają kryteriom automatycznego limitu kredytu, tworzony jest wpis korekty limitu kredytu.

#### <a name="create-automatic-credit-limits"></a>Tworzenie automatycznych limitów kredytu

Umożliwia tworzenie automatycznych limitów kredytu przy użyciu korekt limitu kredytu. Po wybraniu opcji **Generuj \> Automatyczne ograniczenia limitu** wyświetlane jest okno dialogowe, w którym można określić datę wygaśnięcia nowych limitów kredytowych, które będą tworzone na podstawie grup ryzyka, do których są przypisani odbiorcy. Po zakończeniu kliknij przycisk **OK**, aby utworzyć wiersze korekty limitu kredytu.

### <a name="post-adjustments"></a>Księguj korekty

Po utworzeniu wierszy korekty limitu kredytu można skorzystać z przycisku **Księguj** w okienku akcji, aby zaksięgować zapisy i zaktualizować limity kredytowe odbiorców. Jeśli jednak został skonfigurowany przepływ pracy, w okienku akcji należy wybrać opcję **Przepływ pracy \> Prześlij**, aby przesłać arkusz do zatwierdzenia.

### <a name="credit-limit-adjustments-workflows"></a>Przepływy pracy limitu kredytu odbiorcy

Przepływy pracy **Korekty limitu kredytu** mogą być używane do wysyłania korekt limitu kredytu za pomocą procesu zatwierdzania przepływu pracy. Można utworzyć dwa przepływy pracy na stronie **Przepływ pracy zarządzania kredytami** (**Konfiguracja zarządzania kredytami \> Konfiguracje \> Przepływ pracy zarządzania kredytami**):

- **Korekty limitu kredytu** — ten przepływ pracy służy do zatwierdzania wpisów na poziomie nagłówka.
- **Wiersz korekty limitu kredytu** — ten przepływ pracy może służyć do zatwierdzania wpisów korekty, dzięki czemu można je zatwierdzać przez różne osoby, na podstawie kryteriów w przepływie pracy.

> [!NOTE]
> Podczas tworzenia przepływu pracy **Korekty limitu kredytu** można go skonfigurować w taki sposób, aby korekty były księgowane automatycznie po zatwierdzeniu wierszy. Umożliwia uwzględnienie zadania **Księgowania arkusza automatycznie** w przepływie pracy.

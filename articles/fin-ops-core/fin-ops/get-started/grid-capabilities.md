---
title: Możliwości siatki
description: W tym temacie opisano kilka zaawansowanych funkcji formantu siatki. Funkcja nowej siatki musi być włączona, aby można było uzyskać dostęp do tych możliwości.
author: jasongre
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 0fd0e15ea88e9f5f34d8dff82606a8d26616a16d
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260467"
---
# <a name="grid-capabilities"></a>Możliwości siatki

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Nowy formant siatki zapewnia wiele przydatnych i zaawansowanych funkcji, które mogą być używane w celu zwiększenia wydajności użytkowników, tworzenia bardziej interesujących widoków danych oraz uzyskiwania informacji o szczegółowych danych. Ten artykuł będzie obejmował następujące możliwości: 

-  Obliczanie sum
-  Grupowanie danych
-  Pisanie przed systemem
-  Ocenianie wyrażeń matematycznych 

## <a name="calculating-totals"></a>Obliczanie sum
W aplikacjach grupy Finance and Operations użytkownicy mają możliwość wyświetlania sum na dole kolumn liczbowych w siatkach. Sumy te są wyświetlane w sekcji stopki u dołu siatki. 

### <a name="showing-the-grid-footer"></a>Pokazywanie stopki siatki
W dolnej części każdej siatki tabelarycznej w aplikacjach Finance and Operations znajduje się obszar stopki. Stopka może zawierać cenne informacje związane z danymi wyświetlanymi w siatce. Oto kilka przykładów takich informacji:

- Liczba zaznaczonych wierszy w tabeli (gdy zaznaczony jest więcej niż jeden rekord)
- Sumy końcowe u dołu skonfigurowanych kolumn liczbowych
- Liczby kolumn w zestawie danych 

Ta stopka jest domyślnie ukryta, ale można ją łatwo włączyć. Aby wyświetlić stopkę siatki, kliknij prawym przyciskiem myszy nagłówek kolumny w siatce i wybierz opcję **Pokazuj stopkę**. Po włączeniu stopki dla określonej siatki ustawienie to zostanie zapamiętane, dopóki użytkownik nie zdecyduje się na ukrycie stopki, co można wykonać, klikając prawym przyciskiem myszy nagłówek kolumny i wybierając polecenie **Ukryj stopkę**.  Uwaga: umieszczenie akcji **Pokazuj stopkę/Ukryj stopkę** zostanie zmienione w przyszłej aktualizacji. 

### <a name="specifying-columns-with-totals"></a>Określanie kolumn z sumami
Obecnie żadne kolumny nie zostaną skonfigurowane tak, aby domyślnie były wyświetlane sumy. Zamiast tego jest to uważane za jednorazowe działanie konfiguracji, podobne do korygowania szerokości kolumn w siatkach. Po określeniu, że dla kolumny mają być wyświetlone sumy, to ustawienie zostanie zapamiętane przy następnej wizycie na tej stronie.  

Istnieją dwa sposoby skonfigurowania kolumny do wyświetlania sumy: 

- Kliknij prawym przyciskiem myszy kolumnę, dla której chcesz zobaczyć sumę, a następnie wybierz **Suma dla tej kolumny**. Ta akcja powoduje wystąpienie trzech zdarzeń:

    1. Stopka staje się widoczna. 
    2. Twoje preferencje dotyczące wyświetlania sumy dla tej kolumny zostaną zapisane. 
    3. Obliczanie sum jest inicjowane dla tej kolumny i wszystkich innych kolumn, dla których skonfigurowano uprzednio wyświetlanie sum. Czas wymagany do wyświetlenia sumy zależy od rozmiaru zestawu danych do sumowania.

- Po wyświetleniu stopki wybierz opcję **Pokaż sumę** w obszarze stopki u dołu kolumny, dla której ma zostać wyświetlona suma. Jeśli nie ma skonfigurowanych kolumn, przycisk **Pokazuj sumę** będzie dostępny dla wszystkich kolumn liczbowych. 

    Po skonfigurowaniu co najmniej jednej kolumny dla sum, przyciski **Pokaż sumę** będą dostępne tylko przy najechaniu na nie kursorem lub skoncentrowaniu się na nich. Akcja wybranie opcji **Pokaż sumę** powoduje zapisanie preferencji w tej kolumnie, dzięki czemu preferencja będzie stosowana podczas przyszłych odwiedzin na stronie. W stopce ten stan jest wskazywany przez kreskę wyświetlaną w kolumnie. (Jeśli zestaw danych jest wystarczająco mały, suma jest natychmiast pokazywana.)

Jeśli popełnisz błąd i nie chcesz już wyświetlać sumy w określonej kolumnie, kliknij prawym przyciskiem myszy kolumnę i wybierz polecenie **Ukryj sumę** lub wybierz przycisk **Ukryj sumę** w stopce w tej kolumnie. Ta preferencja zostanie również zapisana dla przyszłych odwiedzin na stronie. 

### <a name="calculating-totals"></a>Obliczanie sum
Jeśli zostanie wyświetlona strona z widoczną stopką i kolumny już skonfigurowane dla sum, sumy mogą lub nie być widoczne w stopce. Zachowanie zależy od rozmiaru zestawu danych na stronie. Jeśli zestaw danych jest wystarczająco mały, sumy będą pokazywane automatycznie wraz z liczbą wierszy w zestawie danych. Jeśli w stopce w kolumnach skonfigurowanych dla sum znajdują się kreski, wówczas zestaw danych jest za duży, aby system natychmiastowo pokazywał sumy, a do obliczania sum jest wymagana jawna akcja. W tym celu należy kliknąć przycisk **Oblicz** w stopce lub kliknąć prawym przyciskiem myszy kolumnę, dla której ma zostać obliczona suma, a następnie wybrać opcję **Suma dla tej kolumny**.  

Jeśli obliczanie trwa zbyt długo, można anulować operację, wybierając przycisk **Anuluj**. Czasami jednak ten zestaw danych będzie zbyt duży do obliczania sum (limit narzucony przez Twoją organizację) i zamiast tego użytkownik zostanie powiadomiony o konieczności przefiltrowania danych.

Sumy zostaną automatycznie zaktualizowane podczas aktualizowania, usuwania lub tworzenia wierszy w zestawie danych.  

## <a name="grouping-data"></a>Grupowanie danych
Użytkownicy biznesowi często muszą przeprowadzać analizę danych ad hoc. Chociaż można to zrobić przez wyeksportowanie danych do Microsoft Excel i za pomocą tabel przestawnych, możliwość **Grupowania** w siatkach tabelarycznych umożliwia użytkownikom organizowanie ich danych w interesujące sposoby w aplikacjach Finance and Operations. Ponieważ ta funkcja rozszerza funkcję **Sum**, **Grupowanie** umożliwia również uzyskanie istotnych informacji na temat danych przez zapewnienie sum częściowych na poziomie grupy.

Aby skorzystać z tej funkcji, kliknij prawym przyciskiem myszy kolumnę, według której chcesz grupować, a następnie wybierz polecenie **Grupuj według tej kolumny**. Ta akcja spowoduje posortowanie danych według wybranej kolumny, dodanie nowej Grupy według kolumny do początku do siatki, a następnie wstawienie „wierszy nagłówka” na początku każdej grupy. Te wiersze nagłówka zawierają następujące informacje o każdej grupie: 
-  Wartość danych dla grupy 
-  Etykieta kolumny (Te informacje są szczególnie przydatne po obsłużeniu wielu poziomów grupowania.)
-  Liczba wierszy danych w tej grupie
-  Sumy cząstkowe dla dowolnej kolumny skonfigurowanej do wyświetlania sum

Przy włączonym [Zapisanym widoku](saved-views.md), grupowanie może zostać zapisane przez personalizację jako część widoku, aby uzyskać szybki dostęp przy następnym odwiedzaniu strony.  

Jeśli zostanie wybrana opcja **Grupuj według tej kolumny** w innej kolumnie, oryginalne grupowanie zostało zastąpione, ponieważ tylko jeden poziom grupowania jest obsługiwany w wersji 10.0.9 z aktualizacją platformy 33.

Aby cofnąć grupowanie w siatce, kliknij prawym przyciskiem myszy kolumnę grupowanie i wybierz polecenie **Rozgrupuj**.  


## <a name="evaluating-math-expressions"></a>Ocenianie wyrażeń matematycznych
Jako środek zwiększający produktywność, użytkownicy mogą wprowadzać formuły matematyczne w komórkach liczbowych w siatce. Nie muszą one przeliczać w aplikacji poza systemem. Jeśli na przykład wprowadzisz wartość **=15\*4**, a następnie naciśnij klawisz **Tab**, aby przenieść się z pola, system oszacuje wyrażenie i zapisze wartość **60** dla tego pola.

Aby system rozpoznawał wartość jako wyrażenie, należy uruchomić wartość ze znakiem równości (**=**). Więcej informacji na temat obsługiwanych operatorów i składni zawiera sekcja [obsługiwane symbole matematyczne](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Jak włączyć formant nowej siatki w środowisku? 

**10.0.9/Aktualizacja platformy 33 i późniejsza** Funkcja **Formant nowej siatki** jest dostępna bezpośrednio w module Zarządzanie funkcjami w dowolnym środowisku. Podobnie jak inne funkcje prapremiery publicznej, włączenie tej funkcji w produkcji podlega [uzupełniającemu warunkowi stosowania umowy](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Aktualizacja platformy 32 i 10.0.7 / Aktualizacja platformy 31** Funkcja **Formant nowej siatki** można włączyć w środowiskach warstwy 1 (Dev/Test) i warstwa 2 (piaskownicy) w celu zapewnienia dodatkowych zmian w testowaniu i projekcie, wykonując poniższe kroki.

1.  **Włącz funkcję testową**: wykonaj następującą instrukcję SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Zresetuj usługi IIS**, aby opróżnić statyczną dystrybucję testową pamięci podręcznej. 

3.  **Znajdź funkcję**: przejdź do obszaru roboczego **Zarządzanie funkcjami**. Jeśli **Formant nowej siatki** nie jest wyświetlana na liście wszystkich funkcji, wybierz opcję **Sprawdź aktualizacje**.   

4.  **Włącz funkcję**: Znajdź funkcję **Formant nowej siatki** na liście funkcji i wybierz przycisk **Włącz teraz** w okienku szczegółów. Zauważ, że jest wymagane odświeżenie przeglądarki. 

Wszystkie kolejne sesje użytkownika będą uruchamiane z włączonymi formantami nowej siatki.

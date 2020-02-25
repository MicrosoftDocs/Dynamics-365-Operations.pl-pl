---
title: Możliwości siatki
description: W tym temacie opisano kilka zaawansowanych funkcji formantu siatki. Funkcja nowej siatki musi być włączona, aby można było uzyskać dostęp do tych możliwości.
author: jasongre
manager: AnnBe
ms.date: 01/20/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b49d7823f48bcc9cdbb56b87d5fa72d46ddfa15c
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019951"
---
# <a name="grid-capabilites"></a>Możliwości siatki

[!include [banner](../includes/banner.md)]

Nowy formant siatki zapewnia wiele przydatnych i zaawansowanych funkcji, które mogą być używane w celu zwiększenia wydajności użytkowników, tworzenia bardziej interesujących widoków danych oraz uzyskiwania informacji o szczegółowych danych. Ten artykuł będzie obejmował następujące możliwości: 

-  Obliczanie sum
-  Grupowanie danych
-  Pisanie przed systemem
-  Ocenianie wyrażeń matematycznych 

## <a name="calculating-totals"></a>Obliczanie sum
W aplikacjach grupy Finance and Operations użytkownicy mają możliwość wyświetlania sum na dole kolumn liczbowych w siatkach. Sumy te są wyświetlane w sekcji stopki u dołu siatki. 

### <a name="showing-the-grid-footer"></a>Pokazywanie stopki siatki
Każda siatka tabelaryczna w aplikacjach Finance and Operations zawiera obszar stopki w dolnej części siatki, w którym mogą być widoczne cenne informacje związane z wyświetlanymi danymi. Te informacje to m.in: 
-  Liczba zaznaczonych wierszy w tabeli (gdy zaznaczony jest więcej niż jeden rekord)
-  Sumy końcowe u dołu skonfigurowanych kolumn liczbowych
-  Liczby kolumn w zestawie danych 

Ta stopka jest domyślnie ukryta, ale można ją łatwo włączyć. Aby wyświetlić stopkę siatki, kliknij prawym przyciskiem myszy nagłówek kolumny w siatce i wybierz opcję **Pokazuj stopkę**. Po włączeniu stopki dla określonej siatki ustawienie to zostanie zapamiętane, dopóki użytkownik nie zdecyduje się na ukrycie stopki, co można wykonać, klikając prawym przyciskiem myszy nagłówek kolumny i wybierając polecenie **Ukryj stopkę**.  Uwaga: umieszczenie akcji **Pokazuj stopkę/Ukryj stopkę** zostanie zmienione w przyszłej aktualizacji. 

### <a name="specifying-columns-with-totals"></a>Określanie kolumn z sumami
Obecnie żadne kolumny nie zostaną skonfigurowane tak, aby domyślnie były wyświetlane sumy. Zamiast tego jest to uważane za jednorazowe działanie konfiguracji, podobne do korygowania szerokości kolumn w siatkach. Po określeniu, że dla kolumny mają być wyświetlone sumy, to ustawienie zostanie zapamiętane przy następnej wizycie na tej stronie.  

Istnieją dwa sposoby skonfigurowania kolumny do wyświetlania sumy: 
1.  Kliknij prawym przyciskiem myszy kolumnę, dla której chcesz zobaczyć sumę i wybierz opcję **Suma dla tej kolumny**. Ta akcja spowoduje wykonanie trzech czynności. Po pierwsze, stopka będzie widoczna. Po drugie, system zapisze Twoje preferencje dotyczące wyświetlania sum w tej kolumnie. Po trzecie, ta akcja spowoduje zainicjowanie obliczania sum dla tej kolumny i wszystkich pozostałych wcześniej skonfigurowanych wartości sum. Czas potrzebny do wyświetlenia sumy jest bezpośrednio związany z rozmiarem sumowanego zestawu danych.  

2.  Po wyświetleniu stopki można również kliknąć przycisk **Wyświetl sumę** w obszarze stopki u dołu kolumny, dla której jest wyświetlana suma. Jeśli nie ma skonfigurowanych kolumn, przycisk **Pokazuj sumę** będzie widoczny dla wszystkich kolumn liczbowych. Po skonfigurowaniu co najmniej jednej kolumny dla sum, przyciski **Pokazuj podsumowanie** będą dostępne tylko przy najechaniu na nie lub skoncentrowaniu się na nich. Ta akcja po prostu zapisuje preferencję do wyświetlania sumy w tej kolumnie dla przyszłych odwiedzin na tej stronie, a ten stan jest wskazywany przez kreskę wyświetlaną w tej kolumnie w stopce (lub w polu suma zostanie wyświetlona natychmiast, jeśli zestaw danych jest wystarczająco mały).

Jeśli popełnisz błąd i nie chcesz już wyświetlać sumy w określonej kolumnie, kliknij prawym przyciskiem myszy kolumnę i wybierz polecenie **Ukryj sumę** lub wybierz przycisk **Ukryj sumę** w stopce w tej kolumnie. Ta preferencja zostanie również zapisana dla przyszłych odwiedzin na stronie. 

### <a name="calculating-totals"></a>Obliczanie sum
Jeśli zostanie wyświetlona strona z widoczną stopką i kolumny już skonfigurowane dla sum, sumy mogą lub nie być widoczne w stopce. Zachowanie zależy od rozmiaru zestawu danych na stronie. Jeśli zestaw danych jest wystarczająco mały, sumy będą pokazywane automatycznie wraz z liczbą wierszy w zestawie danych. Jeśli w stopce w kolumnach skonfigurowanych dla sum znajdują się kreski, wówczas zestaw danych jest za duży, aby system natychmiastowo pokazywał sumy, a do obliczania sum jest wymagana jawna akcja. W tym celu należy kliknąć przycisk **Oblicz** w stopce lub kliknąć prawym przyciskiem myszy kolumnę, dla której ma zostać obliczona suma, a następnie wybrać opcję **Suma dla tej kolumny**.  

Jeśli obliczanie trwa zbyt długo, można anulować operację, wybierając przycisk **Anuluj**. Czasami jednak ten zestaw danych będzie zbyt duży do obliczania sum (limit narzucony przez Twoją organizację) i zamiast tego użytkownik zostanie powiadomiony o konieczności przefiltrowania danych.

Sumy zostaną automatycznie zaktualizowane podczas aktualizowania, usuwania lub tworzenia wierszy w zestawie danych.  

## <a name="grouping-data"></a>Grupowanie danych
Użytkownicy biznesowi często muszą przeprowadzać analizę danych ad hoc. Chociaż można to zrobić przez wyeksportowanie danych do Microsoft Excel i za pomocą tabel przestawnych, możliwość **Grupowania** w siatkach tabelarycznych umożliwia użytkownikom organizowanie ich danych w interesujące sposoby w aplikacjach Finance and Operations. Ponieważ ta funkcja rozszerza funkcję **Sum**, **Grupowanie** umożliwia również uzyskanie istotnych informacji na temat danych przez zapewnienie sum częściowych na poziomie grupy.

Aby skorzystać z tej funkcji, kliknij prawym przyciskiem myszy kolumnę, według której chcesz grupować, a następnie wybierz polecenie **Grupuj według tej kolumny**. Ta akcja spowoduje posortowanie danych według wybranej kolumny, dodanie nowej grupy według kolumny do początku do siatki, a następnie wstawienie „wierszy nagłówka” na początku każdej grupy. Te wiersze nagłówka zawierają następujące informacje o każdej grupie: 
-  Wartość danych dla grupy 
-  Etykieta kolumny. Będzie to szczególnie przydatne, gdy jest obsługiwanych wiele poziomów grupowania.  
-  Liczba wierszy danych w tej grupie
-  Sumy cząstkowe dla dowolnej kolumny skonfigurowanej do wyświetlania sum

Przy włączonym [Zapisanym widoku](saved-views.md), grupowanie może zostać zapisane przez personalizację jako część widoku, aby uzyskać szybki dostęp przy następnym odwiedzaniu strony.  

Jeśli zostanie wybrana opcja **Grupuj według tej kolumny** w innej kolumnie, to pierwotne grupowanie zostanie zastąpione, ponieważ tylko poziom grupowania będzie obsługiwany w aktualizacji 10.0.9 / Platform update 33.

Aby cofnąć grupowanie w siatce, kliknij prawym przyciskiem myszy kolumnę grupowanie i wybierz polecenie **Rozgrupuj**.  


## <a name="evaluating-math-expressions"></a>Ocenianie wyrażeń matematycznych
Jako środek zwiększający produktywność, użytkownik może wprowadzać formuły matematyczne w komórkach liczbowych w siatce zamiast wykonywać obliczenia w aplikacji poza systemem. Można na przykład wprowadzić wartość **=15\*4**, a następnie wykroczenie tabulacji w polu. System oceni wyrażenie i zapisze wartość „60” dla pola.

Aby system rozpoznawał wartość jako wyrażenie, należy uruchomić wartość ze znakiem równości (**=**). Więcej informacji na temat obsługiwanych operatorów i składni zawiera sekcja [obsługiwane symbole matematyczne](http://redhivesoftware.github.io/math-expression-evaluator/#supported-maths-symbols).  

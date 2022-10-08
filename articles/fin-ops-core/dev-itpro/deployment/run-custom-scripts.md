---
title: Uruchamiaj własne skrypty X++ z zerowym czasem przestoju
description: Ten artykuł opisuje, jak przesyłać i uruchamiać pakiety instalacyjne, które zawierają niestandardowe skrypty X++ bez konieczności zawieszania systemu.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 3d00f842da69f889738fbcb293c7489bb018e810
ms.sourcegitcommit: f62c9b24c2205d03e2fd6e7c67f7b5c316233b12
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2022
ms.locfileid: "9598090"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Uruchamiaj własne skrypty X++ z zerowym czasem przestoju

[!include [banner](../includes/banner.md)]

Ta funkcja umożliwia wgrywanie i uruchamianie pakietów wdrożeniowych zawierających niestandardowe skrypty X++ bez konieczności przechodzenia przez Microsoft Dynamics Lifecycle Services (LCS) lub zawieszania systemu. Dlatego możesz korygować drobne niespójności danych bez powodowania uciążliwych przestojów.

Korzyścią z używania skryptu X++ do korygowania drobnych niespójności danych jest to, że system po uruchomieniu skryptu automatycznie dostosuje wszystkie powiązane tabele do potrzeb. Takie podejście pomaga zapewnić integralność korekty i minimalizuje ryzyko wprowadzenia nowych niespójności.

> [!IMPORTANT]
> Ta funkcja jest przeznaczona wyłącznie do korygowania drobnych niespójności danych. Nie można go używać do następujących celów ani do innych celów:
>
> - Zbieranie danych
> - Zmiany schematu
> - Migracja danych lub inne procesy o długim przetwarzaniu
> - Poprawianie danych, które mogą być poprawione za pomocą innych środków, takich jak regularne procesy biznesowe, narzędzia spójności danych lub inne narzędzia samoobsługowe
>
> Funkcja ta pozwala autoryzowanym użytkownikom bezpośrednio zmieniać encje i ich rekordy, bez konieczności uruchamiania logiki biznesowej związanej z tymi encjami. Te zmiany mogą powodować problemy z integralnością danych. Dlatego też wasza organizacja może wymagać, abyście przed i/lub po uruchomieniu skryptu uzyskali akceptację i zgodę audytorów wewnętrznych i zewnętrznych (lub innych równorzędnych interesariuszy). Ze względu na zgodność z prawem zmiany, które mają wpływ na niektóre cechy, mogą być także ujawniane w raportach zewnętrznych (takich jak sprawozdania finansowe) lub zgłaszane władzom państwowym. Twoja organizacja ponosi wyłączną odpowiedzialność za wszelkie zmiany, które są wprowadzane do jej danych za pomocą tej funkcji, za wszelkie zatwierdzenia i podpisy lub ujawnienie tych zmian oraz za zgodność z obowiązującym prawem. Użytkownik ponosi wszystkie zagrożenia związane z używaniem tej funkcji.

Wszystkie pakiety do wdrożenia, które są wgrywane do systemu, przechodzą przez obowiązkowy przepływ pracy. Jako środek ostrożności oraz w celu zapewnienia podziału obowiązków użytkownik, który przesyła pakiet do wdrożenia, nie może zatwierdzić go do kolejnych kroków w przepływie pracy. Inny użytkownik musi go zatwierdzić. Jednak po zatwierdzeniu pakietu użytkownik, który go wysłał, będzie mógł wykonać pozostałe kroki.

System wymaga, aby wszystkie pakiety, które można wdrożyć, przeszły przez testowanie. Zanim skrypt będzie mógł zostać uruchomiony na danych produkcyjnych, użytkownik musi sprawdzić, czy dane wyjściowe są poprawne, wybierając **Akceptuj dziennik testowy**. Jeśli dane wyjściowe nie są poprawne, użytkownik musi oznaczyć pakiet jako nieudany, wybierając **Porzuć**. W tym przypadku skrypt nie będzie mógł być uruchomiony na danych produkcyjnych.

Każdy przesłany pakiet jest zapisywany w systemie i przechodzi przez zdefiniowany przepływ zdarzeń. Dla każdego zdarzenia system prowadzi dziennik, który zawiera znacznik czasu oraz tożsamość osoby, która je wykonała. W ten sposób system zapewnia istnienie ścieżki audytu.

Jak pokazuje poniższa ilustracja, system dostarcza szczegółów na temat tego, jak każdy pakiet został uruchomiony w X++ i jakie encje zostały dotknięte.

![Strona Szczegóły skryptu.](media/script-details.png "Strona Szczegóły skryptu")

## <a name="assign-duties-to-users-to-control-access"></a>Przydziel obowiązki użytkownikom, aby kontrolować dostęp

Ta cecha zapewnia następujące zadania. Administratorzy mogą używać tych obowiązków, aby kontrolować dostęp do funkcji.

- **Utrzymywanie własnych skryptów** - Ten obowiązek daje możliwość wgrywania, testowania, weryfikowania i uruchamiania własnych skryptów X++ w środowiskach (testy akceptacyjne użytkowników \[UAT\] oraz produkcja).
- **Zatwierdź skrypty niestandardowe** – ten obowiązek udziela możliwości zatwierdzania przekazanego niestandardowego skryptu X++. Zatwierdzenie jest obowiązkowym krokiem, zanim jakikolwiek skrypt będzie mógł zostać przetestowany, zweryfikowany i uruchomiony.

Aby zminimalizować ryzyko złośliwych działań, każdy skrypt musi być wyraźnie zatwierdzony przez użytkownika innego niż ten, który go załadował. Zanim będziesz mógł korzystać z tej funkcji w swojej organizacji, administrator musi przydzielić powyższe obowiązki co najmniej dwóm odpowiednim i wysoce zaufanym użytkownikom. Mimo że jeden użytkownik może pełnić obie te funkcje, nadal nie będzie mógł zatwierdzać swoich własnych skryptów.

## <a name="create-a-deployable-package"></a>Tworzenie wdrażalnego pakietu

Funkcja ta wymaga zwykłego pakietu wdrożeniowego, który może być utworzony w Visual Studio. Aby uzyskać więcej insstrukcji, zobacz [Tworzenie wdrażalnych pakietów modeli](../deployment/create-apply-deployable-package.md).

Twój pakiet do zainstalowania musi zawierać dokładnie jedną możliwą do uruchomienia klasę X++. Innymi słowy, musi mieć jedną klasę, która zawiera metodę o następującym podpisie.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> Nazwa metody głównej musi być napisana małymi literami.

## <a name="code-example"></a>Przykład kodu

Poniższy przykład kodu pokazuje, jak może być zbudowany pakiet, który można wdrożyć.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Najlepsze wskazówki

Poniższa lista opisuje kilka najlepszych praktyk skutecznego pisania, wdrażania i uruchamiania skryptów. Lista ta nie jest wyczerpująca i powinna być traktowana jedynie jako wskazówka.

- **Należy** napisać wiadomość o sukcesie na końcu skryptu. W ten sposób będziesz mógł zobaczyć, że skrypt przebiegł bez wyjątków.
- **Należy** dodać jawną obsługę zakresu transakcji.
- **Należy** używać istniejącej logiki biznesowej, takiej jak metody`update()`, ale **nie** omijaj logiki biznesowej używając metod `doUpdate()`, `doInsert()` i `doDelete()`. Takie podejście pomoże zapewnić, że dane zależne będą traktowane poprawnie. Zmniejszy to także znacząco ryzyko dalszych niespójności danych.
- **Należy** zapewnić kontekst towarzystwa. Takie podejście ujawni typowe błędy w trakcie działania skryptu. Na przykład ujawni, czy skrypt jest uruchamiany w niewłaściwej firmie.
- **Zapewnij**, że liczba dotkniętych rekordów jest zgodna z Twoimi oczekiwaniami. Takie podejście ujawni, czy w trakcie przygotowywania scenariusza nie doszło do nieoczekiwanego przesunięcia danych w systemie.
- **Nie** używaj unikalnych nazw klas dla każdego skryptu (np. poprzez umieszczenie w nazwie odwołania do elementu pracy). Takie podejście zapobiegnie problemom związanym z kolizją nazw podczas przesyłania skryptu. Jeśli potrzebna jest nowa iteracja skryptu, pamiętaj, by nadać mu nową nazwę.
- **Najpierw** należy przetestować każdy skrypt w środowisku nieprodukcyjnym. Testuj pod kątem zamierzonego wpływu i niezamierzonych efektów ubocznych na powiązane dane. Upewnij się, że wszystkie procesy biznesowe, na które mogą mieć wpływ, będą mogły być pomyślnie i w pełni zakończone po ich zakończeniu.

## <a name="upload-and-run-a-deployable-package"></a>Wgranie i uruchomienie pakietu do zainstalowania

Użyj poniższej procedury, aby załadować i uruchomić skrypt.

1. W aplikacjach finansowych i operacyjnych przejdź do zakładki **Administracja systemu \> Zadania okresowe \> Baza danych \> Skrypty własne**.
1. Wybierz pozycję **Przekaż**.
1. Wybierz pakiet instalacyjny, który utworzyłeś tak, jak opisano wcześniej w tym artykule. Zostanie wyświetlony monit o określenie celu skryptu.
1. Skrypt musi być teraz zatwierdzony przez innego użytkownika niż ten, który go załadował. Zatwierdzający musi wykonać poniższe kroki:

    1. Przejdź do **Administracja systemu \> Okresowe \> Baza danych \> Skrypty własne**.
    1. Wybierz skrypt do zatwierdzenia, a następnie wybierz przycisk **Szczegóły**.
    1. Na Polu Akcji, na zakładce **Przepływy**, w grupie **Rozpocznij** wybierz **Zatwierdź** lub **Odrzuć**. Jeśli wybierzesz opcję **Zatwierdź**, skrypt będzie oznaczany jako zatwierdzony i odblokowany do testowania. W przypadku wybrania opcji **Odrzuć** skrypt jest zablokowany. W obu przypadkach zdarzenie jest rejestrowane, a kopia skryptu jest przechowywana w systemie.

1. Skrypt musi zostać przetestowany, aby upewnić się, że robi to, co do niego należy. Testerem może być ten sam użytkownik, co przesyłający lub zatwierdzający, albo może to być trzeci użytkownik, który ma wymagane uprawnienia. Próbnik musi wykonać poniższe kroki:

    1. Przejdź do **Administracja systemu \> Okresowe \> Baza danych \> Skrypty własne**.
    1. Wybierz skrypt do przetestowania, a następnie wybierz przycisk **Szczegóły**.
    1. Na Polu Akcji, na zakładce **Przepływ pracy**, w grupie **Test** wybierz **Rozpocznij test**. Skrypt jest uruchamiany wewnątrz tymczasowej transakcji, którą system automatycznie przerwie, gdy będzie zbierał różne logi i polecenia SQL.
    1. Kiedy skrypt zakończy działanie, przejrzyj logi i sprawdź, czy wyniki spełniają Twoje oczekiwania. Wykonaj jeden z następujących kroków:

        - Jeśli jesteś zadowolony z wyniku testu, wybierz **Akceptuj dziennik testu** w grupie **Test** na zakładce **Przepływ pracy** w Panelu akcji, aby umożliwić uruchomienie skryptu. Dziennik zdarzeń będzie odzwierciedlał fakt, że skrypt został przetestowany, a także wskaże, kto i kiedy go przetestował.
        - Jeśli nie jesteś zadowolony z wyniku testu, wybierz **Zatrzymaj** w grupie **Zakończ** na zakładce **Proces roboczy** w Panelu akcji, aby nie dopuścić do uruchomienia skryptu. System będzie przechowywał kopię skryptu wraz z zapisem jego historii.

1. Gdy jesteś pewien, że skrypt spełnia Twoje oczekiwania, wybierz **Uruchom** w grupie **Uruchom** na zakładce **Proces roboczy** w Panelu akcji, aby go uruchomić. To polecenie robi to samo, co poprzedni test, ale na końcu transakcja zostanie zatwierdzona.
1. Po zakończeniu działania skryptu sprawdź wynik i potwierdź, że skrypt zadziałał zgodnie z Twoimi założeniami. Wykonaj jeden z następujących kroków:

    - Jeśli jesteś zadowolony z rezultatu, zaznacz **Cel rozwiązany** w grupie **Zakończenie** na zakładce **Proces pracy** w Panelu Akcji. Dziennik zdarzeń będzie zawierał informację o tym, że skrypt został wykonany pomyślnie oraz wskaże, kto i kiedy go zweryfikował. Skrypt zostaje zapisany, ale jest teraz zablokowany i nie można go ponownie uruchomić.
    - Jeśli nie jesteś zadowolony z rezultatu, zaznacz **Cel nierozwiązany** w grupie **Zakończ** na zakładce **Przebieg pracy** w Panelu akcji. Dziennik zdarzeń będzie zawierał informację o tym, że skrypt nie spełnił swojego zadania, oraz wskaże, kto i kiedy go uruchomił. Skrypt zostaje zapisany, ale jest teraz zablokowany i nie można go ponownie uruchomić. System nie cofa jednak automatycznie działania skryptu. Być może będziesz musiał napisać, zaimportować i uruchomić nowy skrypt, aby cofnąć efekt, jaki nieudany skrypt wywarł na twój system.

Twój wybór w ostatnim kroku definiuje ostateczny stan skryptu. Możesz powtarzać ten proces tak, jak tego potrzebujesz.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Prześlij i uruchom pakiet instalacyjny przez LCS

Zamiast wdrożenia pakietu przez interfejs użytkownika Twoich aplikacji finansowych i operacyjnych, jak opisano w poprzedniej sekcji, możesz wgrać go do LCS i użyć normalnej procedury, aby go wdrożyć. Więcej informacji: [Instalowanie wdrażalnych pakietów z wiersza polecenia](../deployment/install-deployable-package.md).

Chociaż to podejście ma mniej ograniczeń, to zapewnia mniejszą ochronę przed błędami. Dodatkowo, ponieważ wymaga to restartu wszystkich serwerów, spowoduje to pewne przestoje.


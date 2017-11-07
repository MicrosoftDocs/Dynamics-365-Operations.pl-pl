---
title: Generowanie raportu finansowego
description: Ten temat zawiera informacje o generowaniu sprawozdania finansowego.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 01bb8999e5d9c0e16f133a621ebfe1d102565f2f
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="generate-a-financial-report"></a>Generowanie raportu finansowego

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o generowaniu sprawozdania finansowego. 

Aby wygenerować raport, otwórz definicję raportu, a następnie kliknij przycisk Generuj na pasku narzędzi. Okno Stan kolejki raportów otworzy się i wskaże lokalizację raportu w kolejce. Domyślnie wygenerowany raport zostanie otwarty w przeglądarce sieci web.
| ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**        |
|------------------------------------------------------------------------------------------------|
| Można generować raporty tylko do folderów i lokalizacji, do których masz uprawnienia dostępu. |

W poniższej tabeli wyjaśniono opcje dostępne do generowania raportów.

| Opcja                                                                                | Więcej informacji |
|---------------------------------------------------------------------------------------|----------------------|
| Konfigurowanie harmonogramu w celu automatycznego generowania raportu lub grupy raportów              |                      |
| Sprawdzanie brakujących kont lub danych w raporcie i sprawdzanie poprawności raportu |                      |

Podczas generowania raportu są używane opcje, które określono na kartach Definicja raportu. Karta Produkcja i dystrybucja pozwala określić lokalizację biblioteki raportów, która zapewnia prosty sposób udostępniania raportu.

## <a name="schedule-report-generation"></a> Generowanie raportu planu
Wiele firm ma podstawowy zbiór raportów, które są uruchamiane w zaplanowanych okresach, w celu dostosowania ich procesów biznesowych. Można zaplanować raport do generowania regularnego, np. codziennie, co tydzień, co miesiąc lub co roku. Sesja może obejmować jeden raport albo grupę raportów dla kilku przedsiębiorstw. Dla każdej uwzględnionej firmy, na przykład wpisanej w definicji drzewa raportowania, trzeba wprowadzić poświadczenia dostępu. Jeśli poświadczenia nie są prawidłowe, raport wyświetli tylko informacje, że masz uprawnienia dostępu, takie jak firma w której jesteś zalogowany w danej chwili. Informacje o danych wyjściowych są odczytywane najpierw z grupy raportów, a następnie z poszczególnych raportów.

Tworzone i zapisywane raporty są wyświetlane w okienku nawigacji w obszarze Harmonogramy raportów. W celu uporządkowania raportów można tworzyć foldery. Jeśli nie działa jeden raport w harmonogramie, wszystkie pozostałe raporty będą dalej działały.
| ![Ważne](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Ważne")**Ważne**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Do tworzenia, modyfikowania i usuwania harmonogramów raportów wymagana jest rola projektanta lub administratora. Po uruchomieniu raportu poświadczenia użytkownika, który utworzył harmonogram, są używane do generowania raportu. |

### <a name="create-a-report-schedule"></a>Tworzenie harmonogramu raportu

1.  W Projektancie raportów w menu Plik kliknij przycisk Nowy, a następnie wybierz opcję Harmonogram raportu. Zostanie otwarte okno dialogowe Nowy harmonogram raportu.
2.  W obszarze Ustawienia wybierz pojedynczy raport lub grupę raportów do zaplanowania. Masz dostęp tylko do raportów/grup raportów dotyczących firmy lub zbioru modułów konstrukcyjnych, gdzie obecnie jesteś zalogowanym użytkownikiem.
3.  Zaznacz pole wyboru Aktywny. Harmonogram raportu zostanie włączony. Aktywacji i dezaktywacji harmonogramu raportu może dokonywać wyłącznie jego twórca lub administrator.
4.  Kliknij przycisk Uprawnienia i wprowadź poświadczenia logowania do firmy. Domyślnie są używane poświadczenia logowania do firmy, gdzie obecnie jesteś zalogowanym użytkownikiem. Jeśli raport ma objąć także inne firmy, na przykład podane w definicji drzewa raportowania, zaznacz pole wyboru Użyj osobnych poświadczeń, po czym wprowadź poświadczenia logowania do wszystkich pozostałych firm. Możesz zaznaczyć opcję Uwierzytelnianie systemu Windows albo wpisz nazwę użytkownika i hasło osobno dla każdej firmy. Zaznacz pole wyboru Zapisz poświadczenia, aby zapisać poświadczenia dla tych firm, a następnie kliknij przycisk OK, aby zamknąć okno dialogowe.
5.  W obszarze Częstotliwość w polu Początek cyklu wybierz dzień, gdy harmonogram ma się uruchomić. Domyślnie jest ustawiana bieżąca data systemowa z komputera klienckiego.
6.  W polu Uruchom raport o zaznacz godzinę, o której ma być wykonywany raport. Jeśli wprowadzisz godzinę wcześniejszą niż bieżąca godzina systemowa, raport zostanie po raz pierwszy wykonany w następnym zaplanowanym dniu.
7.  W obszarze Wzorzec cyklu określ częstotliwość wykonywania raportu. Domyślnie wybrana jest opcja Codziennie z wartością 1 dla opcji Interwał (w dniach). Inne dostępne opcje to Co tydzień, Co miesiąc i Co rok.
8.  W obszarze Zakres cyklu określ długość okresu, przez jaki raport ma być generowany.
    -   Brak daty zakończenia — harmonogram raportu nie wygasa.
    -   Ustalona liczba wystąpień — raport jest generowany określoną liczbę razy, po czym następuje jego dezaktywacja.
    -   Koniec do — harmonogram wykonywania raportu kończy się w określonym dniu.

9.  Na pasku narzędzi kliknij przycisk Zapisz. W oknie dialogowym Zapisz jako wprowadź unikatową nazwę i opis dla harmonogramu raportu.

Do kopiowania harmonogramu raportu wymagana jest rola projektanta lub administratora. Nawet wtedy, gdy administrator zmienia harmonogram raportu, raport przyjmuje poświadczenia użytkownika, który utworzył raport.
### <a name="copy-a-report-schedule"></a>Kopiowanie harmonogramu raportu

1.  W Projektancie raportów, kliknij Harmonogramy raportów w okienku nawigacji i otwórz raport planowanie do skopiowania.
2.  Z menu Plik wybierz polecenie Zapisz jako, a następnie w oknie dialogowym Zapisywanie jako nadaj harmonogramowi nową nazwę i wprowadź opis. Kliknij przycisk OK. Nowy harmonogram pojawi się w okienku nawigacji.
3.  W nowym harmonogramie zmień pola i informacje według potrzeb, a następnie kliknij Zapisz na pasku narzędzi lub kliknij Zapisz w menu Plik.

Aby usunąć harmonogram raportu, musisz być właścicielem harmonogramu raportu lub mieć rolę administratora.
### <a name="delete-a-report-schedule"></a>Usuwanie harmonogramu raportu

1.  W Projektancie raportów kliknij Harmonogramy raportów w okienku nawigacji.
2.  Zaznacz harmonogram raportu, który chcesz skasować, i kliknij przycisk Usuń lub naciśnij klawisz Delete.
3.  W oknie dialogowym weryfikacji zamiaru usunięcia kliknij przycisk Tak. Harmonogram raportu zostanie trwale usunięty. Jeśli nie masz uprawnień do usuwania harmonogramu, wyświetlany jest komunikat, a raport nie jest usuwany.

### <a name="credentials-and-report-schedules"></a>Poświadczenia i harmonogramy raportów

Jeśli nie wprowadzisz poświadczeń, które są wymagane dla wszystkich firm uwzględnionych w raportach, podczas zapisywania harmonogramu raportu wyświetlony zostanie następujący komunikat: „Wprowadź poświadczenia dla firm, które są zawarte w harmonogramie tego raportu. Kliknij przycisk Uprawnienia i wprowadź poświadczenia”.

Na przykład Phyllis loguje się do Firmy A za pomocą swojego loginu i hasła. Tworzy harmonogram dla raportu, który używa definicji drzewa raportowania do zbierania danych z wielu firm. Podczas zapisywania harmonogramu Anna zobaczy monit o wprowadzenie poświadczeń logowania do innych firm wymienionych w definicji drzewa raportowania. Po upływie limitu czasu poświadczenia, odpowiednie raporty w harmonogramie raportu nie są generowane do momentu aż poświadczenia zostaną zaktualizowane. O konieczności aktualizacji uprawnień informuje komunikat wyświetlany w kolejce raportów. Harmonogram raportu nie powiedzie się, jeśli wystąpi którykolwiek z następujących scenariuszy (ponieważ wymagają one poświadczeń):
-   Nowa firma została dodana do drzewa raportu dla konkretnego raportu.
-   Zmodyfikowanie raportu w drzewie raportów.
-   Dodanie do grupy raportów nowego raportu obejmującego dodatkową firmę.

Aby kontynuować, kliknij przycisk Uprawnienia w oknie dialogowym Planowanie raportu, a następnie wprowadź odpowiednie poświadczenia.

## <a name="missing-account-analysis-feature"></a>Funkcja analizy brakujących kont
Można wyszukiwać konta finansowe i wymiary, których może brakować we wszystkich definicjach wierszy, definicjach drzew raportowania i definicjach raportów w grupie bloków konstrukcyjnych. Jest to przydatne, jeśli tworzysz lub aktualizujesz kilka kont lub bloków konstrukcyjnych w krótkim okresie, a chcesz zweryfikować, że wszystkie nowe informacje są uwzględnione w raportach.

Brakujące konta są określane przy użyciu najniższej i najwyższej wartości z definicji wiersza lub definicji drzewa raportowania. Następnie program wyświetla listę kont, których nie ma w definicji wiersza lub definicji drzewa raportowania, ale które występują w danych finansowych. Jeśli brakujące konto jest większe lub mniejsze od wartości w definicji wiersza, to konto nie jest uwzględniane na liście brakujących kont.
| ![Porada](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Porada")**Porada**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Na potrzeby sprawdzania ten proces powinien być uruchomiony przed wygenerowaniem miesięcznych raportów i podczas tworzenia bloków konstrukcyjnych. |

W raportach, które mają zakresy wartości, jest mniejsze prawdopodobieństwo brakujących kont. Jeśli to możliwe, używaj zakresów w blokach konstrukcyjnych, aby dodawać nowe konta podczas ich tworzenia. Jeśli jakikolwiek raport jest ustawiony na firmę @ANY, możesz zalogować się do określonej firmy i uruchomić analizę brakujących kont dla tej firmy.
| ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Po dodaniu nowej firmy należy ją dodać do drzew raportowania we wszelkich istniejących raportach. W przeciwnym razie firma nie zostanie uwzględniona w analizie brakujących kont. |

### <a name="run-missing-account-analysis"></a>Uruchamianie analizy brakujących kont

1.  W Projektancie raportów kliknij Narzędzia, a następnie kliknij Analizy brakujących kont.
2.  W polu Filtr firm wybierz firmę, dla której będą filtrowane wyniki, lub zaznacz opcję Wszystko (brak filtru), aby wyświetlić wyniki ze wszystkich dostępnych firm.
3.  W polu Filtr wymiarów wybierz wymiar, dla którego będą filtrowane wyniki, lub zaznacz opcję Wszystko (brak filtru), aby wyświetlić wszystkie informacje o wymiarach dla wszystkich dostępnych wymiarów.
4.  W polu Grupuj wg zaznacz opcję sortowania wyników. Wyniki można sortować zgodnie z modułem konstrukcyjnym, którego to dotyczy, lub według zestawów wymiarów i wartości.
5.  Przegląd wyświetlanych wyników. Gdy w górnym okienku zostanie zaznaczony element, w dolnym okienku pojawią się dodatkowe informacje o wyjątku. Obejmują one powiązane wymiary, wartości i raporty.
6.  Aby otworzyć element, którego dotyczy problem, kliknij skojarzoną ikonę widoczną w okienku listy, lub kliknij element prawym przyciskiem myszy i wybierz Otwórz. Aby zaznaczyć wiele elementów, przytrzymaj klawisz Ctrl podczas zaznaczania elementów w dolnym okienku.
7.  Jeśli analiza zwróci wartości, bloki konstrukcyjne lub raporty, których nie powinno w niej być, kliknij element prawym przyciskiem myszy i wybierz Wyklucz lub zaznacz pole wyboru Wykluczyć obok elementu, aby usunąć go z listy. Wykluczone elementy nie są uwzględniane podczas odświeżania listy. Aby zaznaczyć wiele elementów, przytrzymaj klawisz Ctrl podczas zaznaczania elementów w dolnym okienku. Aby wyświetlić wszystkie elementy, w tym wszystkie wyniki, które wcześniej zostały wykluczone z analizy, zaznacz pole wyboru Pokaż wykluczone bloki konstrukcyjne i wartości, a następnie kliknij Odśwież.
8.  Kliknij przycisk Odśwież, aby odświeżyć określone wyjątki. Kliknij Tak, aby wykonać pełne odświeżenie wszystkich wyników, lub kliknij przycisk Nie, aby wykonać częściowe odświeżenie wskazanych elementów.
    | ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**                    |
    |------------------------------------------------------------------------------------------------------------|
    | Formularz jest automatycznie odświeżany po jego otwarciu, chyba że formularz został otwarty w ciągu ostatnich 15 minut. |

9.  Gdy problem zostanie rozwiązany, kliknij OK, aby zamknąć okno dialogowe.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Skróty klawiaturowe dla analizy brakujących kont
Po uruchomieniu analizy brakujących kont dostępne są następujące skróty klawiaturowe.

| Funkcja                           | Użyj tego skrótu klawiaturowego |
|--------------------------------------|----------------------------|
| Filtruj według firm                    | Alt+C                      |
| Filtruj według wymiarów                  | ALT+D                      |
| Wybierz pole Grupuj wg            | Alt+G                      |
| Pokaż wykluczone moduły i wartości      | Alt+S                      |
| Odśwież wyniki                      | Alt+R                      |
| Wyklucz wybrany moduł konstrukcyjny  | Alt+X                      |
| Wyklucz wybraną definicję wiersza  | Ctrl+B                     |
| Wyklucz wybraną wartość wymiaru | Ctrl+D                     |
| Otwórz wybraną definicję raportu  | Ctrl+R                     |
| Otwórz wybraną definicję wiersza     | Ctrl+O                     |

 
<a name="see-also"></a>Informacje dodatkowe
--------

[Raporty finansowe](financial-reporting-intro.md)

[Interfejs Projektanta raportów](report-designer-interface.md)




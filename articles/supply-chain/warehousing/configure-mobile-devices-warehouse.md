---
title: Konfigurowanie urządzeń przenośnych do pracy magazynowej
description: W tym temacie opisano sposób konfigurowania elementów menu, których pracownicy magazynu używają do wykonywania różnych czynności na urządzeniach przenośnych.
author: MarkusFogelberg
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acf5e191f1d4b12a59490a5ab8f222c5351886c33eedcb8833921541d1bda7d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736582"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Konfigurowanie urządzeń przenośnych do pracy magazynowej

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania elementów menu, których pracownicy magazynu używają do wykonywania różnych czynności na urządzeniach przenośnych.

> [!NOTE]
> Ten temat dotyczy funkcji w module Zarządzanie magazynem. Nie ma zastosowania do funkcji w module Zarządzanie zapasami. Elementy menu, które pojawiają się w menu na urządzeniu przenośnym w magazynie, konfiguruje się na stronie **Elementy menu urządzenia przenośnego**. Ponieważ elementy menu mogą być umieszczane w różnych menu, można łatwo skonfigurować struktury menu, tak aby tylko określone typy pracy były dostępne dla określonych użytkowników. Konfiguracja elementów menu może obejmować następujące funkcje:

- Przetwarzanie informacji lub wykonanie działań, np. drukowanie etykiety, generowanie numerów identyfikacyjnych, rozpoczęcia zlecenia produkcyjnego lub szybkie wyszukiwanie informacje o pozycji w lokalizacjach.
- Tworzenie pracy, która zostanie wykonana za pomocą innego procesu. Na przykład przyjęcie towaru dla zamówienia zakupu może tworzyć pracę odkładania dla innego pracownika.
- Wykonywanie pracy, która została utworzona przez inny proces (istniejącej pracy), np. pracy odłożenia, która została utworzona podczas odbierania towarów dla zamówienia zakupu.

Aby utworzyć element menu dla działania lub zapytania, należy wybrać w polu **Tryb** wartość **Pośredni**. Zostanie wtedy udostępniona lista opcji **Kod działania**, umożliwiając wybranie typu zapytania lub działania, którego dotyczy element menu. Aby utworzyć element menu do generowania pracy magazynu, należy ustawić w polu **Tryb** wartość **Praca**. Zostanie wyświetlona lista opcji **Proces tworzenia pracy**. Aby utworzyć element menu do przetwarzania istniejącej pracy magazynu, należy ustawić pole **Tryb** na **Praca**, a następnie ustawić opcję **Użyj istniejącej pracy** na **Tak**. 

> [!NOTE]
> W zależności od trybu wybranego dla elementu menu i jeśli służy on do wykonywania istniejącej pracy, dodatkowe pola są dostępne dla tego elementu menu. Informacje o dodatkowych polach wyboru można znaleźć w sekcji „Dodatkowe opcje elementów menu” w tym temacie.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Konfigurowanie elementów menu pod kątem działań i zapytań

Jeśli pole **Tryb** dla elementu menu jest ustawione na **Pośredni**, można utworzyć element menu do wykonywania działań lub zapytań, które nie tworzą pracy. Może to być np. ponowne drukowanie etykiet numerów identyfikacyjnych czy zapytanie o towary w lokalizacji. W poniższej tabeli przedstawiono dostępne opcje.

| Opcja | Opis |
|---|---|
| Brak | Ta wartość domyślna nie powoduje włączenia zapytania ani działania. |
| Informacje | Służy do wyświetlania informacji o systemie, takie jak numer wersji, identyfikator magazynu oraz pracownika, który jest aktualnie zalogowany. |
| Zmień magazyn | Służy do zmieniania magazyny, w którym pracownik jest zalogowany. |
| Zapytanie o lokalizację | Służy do wyświetlania informacji o wszystkich towarach i ich ilościach w lokalizacji. |
| Zapytanie o numer identyfikacyjny | Służy do wyświetlania ilości towarów dla numeru identyfikacyjnego oraz lokalizacji numeru identyfikacyjnego. |
| Rozpocznij zlecenie produkcyjne | Służy do uruchamiania zlecenia produkcyjnego. |
| Odpadki produkcji | Służy do wprowadzania ilości odpadków powstałych podczas produkcji dla poszczególnych wierszy listy składowej (BOM). |
| Produkcja ostatniej palety | Wskazuje, że został została wyprodukowana ostatnia paleta towarów dla zlecenia produkcyjnego i należy zaktualizować stanu zlecenia produkcyjnego do **zgłoszonego jako zakończone**. Stan surowców, które nie zostały zużyte podczas procesu produkcyjnego zostanie przywrócony z **Pobrane** do **Zamówione**, a towary mogą być zwracane do magazynu. |
| Zapytanie o pozycję | Służy do skanowania towarów w celu określenia ich miejsca w magazynie. Zapytanie zwraca wszystkie lokalizacje i ilości skanowanego towaru. |
| Ponownie drukuj etykietę | Służy do ponownego drukowania numerów identyfikacyjnych. |
| Kompilacja numerów identyfikacyjnych | Służy do tworzenia nadrzędnego numeru identyfikacyjnego przez łączenie wielu numerów identyfikacyjnych w tej samej lokalizacji. Ta opcja przydaje się, jeśli przenosisz wiele numerów identyfikacyjnych jednocześnie. Po przeniesieniu nadrzędnego numeru identyfikacyjnego musisz podzielić numer identyfikacyjny zanim będzie można podjąć z niego towary. <p></p>**Wskazówka:** Aby przenieść nadrzędny numer identyfikacyjny, musisz użyć urządzenia przenośnego, które jest skonfigurowane do tworzenia pracy przenoszenia. |
| Przerwa dotycząca numeru identyfikacyjnego | Podziel kompilację numeru identyfikacyjnego, żeby podjąć towary z numerów identyfikacyjnych, które były w tej kompilacji. |
| Zaewidencjonowanie kierowcy | Jeśli używasz modułu Zarządzanie transportem, zarejestruj przybycie kierowcy, skanując identyfikator ładunku wychodzącego, identyfikator terminu dostawy lub identyfikator wysyłki. Dla tej opcji ładunek musi być przypisany do terminu dostawy i musi mieć stan **Załadowany**. |
| Wyewidencjonowanie kierowcy | Umożliwia rejestrowanie dotrzymania terminu przez kierowcę. |
| Pamięć podręczna usuwania sekwencji numerów | Usuń cyfry sekwencji numerów z pamięci podręcznej sekwencji numerów. To działanie jest zwykle wykonywane przez administratora systemu, aby rozwiązać problemy podczas korzystania z urządzeń przenośnych. |
| Zmień dyspozycję partii | Umożliwia zezwolenie pracownikom na określenie kodu dyspozycji partii dla towaru i partii. Wybranie tej opcji spowoduje zaktualizowanie kodu dyspozycji określony dla danej partii. |
| Wyświetl listę otwartych prac | Umożliwia wyświetlenie listy dostępnych pracy dla określonego użytkownika. Użytkownik może następnie wybrać pracę do wykonania i zostanie do niej przekierowany. Tę listę można wyświetlać na tabletach z ekranem o przekątnej co najmniej 7 cali. Po wybraniu tej opcji pozycje menu **Edytuj kwerendę** i **Lista pól** staną się dostępne. Strona **Edycji kwerendy** umożliwia skonfigurowanie kryteriów pracy, która znajduje się na liście. Strona **Listy pól** umożliwia wybranie, które pola będą wyświetlane na liście prac. Przykładowo można zmniejszyć liczbę widocznych pól, aby użytkownik mógł szybciej wybrać najodpowiedniejszą pozycję pracy. Na skróconej karcie **Ogólne** w polu **Rekordy na stronie** można też wybrać, ile rekordów pracy jest wyświetlanych na stronie. Jeśli opcja **Zezwalaj użytkownikom na filtrowanie pracy według typu transakcji** jest zaznaczona, lista pracy będzie zawierała formant **Filtruj pracę**, który umożliwia filtrowanie według typu transakcji. Na liście pracy użytkownik widzi tylko te prace, do których ma uprawnienia dostępu. Należy się upewnić, że ma on uprawnienia do co najmniej jednej pozycji menu sterowanej przez użytkownika obsługującej określone typy klasy pracy, do których powinien mieć dostęp. Uprawnienia są sprawdzane również wtedy, gdy użytkownik próbuje wykonać pracę z listy.|
| Utwórz zamówienie przeniesienia z numery identyfikacyjnego | Umożliwia pracownikom magazynu tworzenie i przetwarzanie zamówień przeniesienia bezpośrednio z poziomu aplikacji Warehouse Management. Pracownicy magazynu rozpoczynają od wybrania magazynu docelowego i mogą skanować jeden lub więcej numerów identyfikacyjnych za pomocą aplikacji. Gdy pracownik magazynu wybierze **Zakończ zamówienie**, zadanie wsadowe utworzy wymagane zamówienie przeniesienia i wiersze zamówienia na podstawie dostępnych zapasów zarejestrowanych dla tych numerów identyfikacyjnych. Aby uzyskać więcej informacji, zobacz temat [Tworzenie zamówień przeniesienia z aplikacji magazynowej](create-transfer-order-from-warehouse-app.md)

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Konfigurowanie elementów menu do tworzenia pracy dla innego pracownika lub procesu

Możesz skonfigurować element menu, który tworzy pracę dla innego pracownika po wykonaniu działania początkowego na urządzeniu przenośnym. Na przykład gdy jeden pracownik przyjmuje towar za pomocą urządzenia przenośnego, dla innego pracownika tworzona jest praca odłożenia. Aby skonfigurować element menu, który tworzy pracę, na stronie **Elementy menu urządzenia przenośnego** w polu **Tryb** trzeba wybrać **Praca**. W poniższej tabeli opcje w polu **Proces tworzenia pracy** są rozmieszczane według typu zlecenia.

<table>
<tbody>
<tr>
<th>Typ zlecenia</th>
<th>Opcja</th>
<th>Opis</th>
</tr>
<tr>
<td rowspan="8">Zamówienie zakupu</td>
<td>Przyjęcie wiersza zamówienia zakupu</td>
<td>Zarejestruj odbiór ilości towaru za pomocą numeru zamówienia zakupu i numeru wiersza zamówienia zakupu i utwórz pracę odłożenia dla innego pracownika.</td>
</tr>
<tr>
<td>Przyjęcie i odłożenie wiersza zamówienia zakupu</td>
<td>Zarejestruj odbiór ilości towaru za pomocą numeru zamówienia zakupu i numeru wiersza zamówienia zakupu i odłóż towary. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td>Przyjęcie pozycji z zamówienia zakupu</td>
<td>Zarejestruj odbiór ilości towaru dla zamówienia zakupu, rejestrując numer zamówienia zakupu i numeru towaru, i utwórz pracę odłożenia dla innego pracownika.</td>
</tr>
<tr>
<td>Przyjęcie i odłożenie pozycji z zamówienia zakupu</td>
<td>Zarejestruj odbiór ilości towaru dla zamówienia zakupu, rejestrując numer zamówienia i numer towaru i odłóż towar. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td>Przyjęcie numeru identyfikacyjnego</td>
<td>Odbierz przychodzące wcześniejsze powiadomienie o wysyłce (WPW) za pomocą numeru identyfikacyjnego.</td>
</tr>
<tr>
<td>Odbieranie numeru identyfikacyjnego i odłożenie</td>
<td>Odbierz i odłóż przychodzące wcześniejsze powiadomienie o wysyłce (WPW) za pomocą numeru identyfikacyjnego.</td>
</tr>
<tr>
<td>Odbierana pozycja ładunku</td>
<td>Zarejestruj przyjęcie ilości towaru dla ładunku za pomocą identyfikatora ładunku, a następnie utwórz pracę odłożenia dla innego pracownika. Numer towaru i wymiary produktu odpowiadają wierszom na zamówieniu zakupu.</td>
</tr>
<tr>
<td>Odbierana i odłożona pozycja ładunku</td>
<td>Zarejestruj przyjęcie ilości dla ładunku za pomocą identyfikatora ładunku i odłóż towary. Numer towaru i wymiary produktu odpowiadają wierszom na zamówieniu zakupu. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td rowspan="2">Zwróć zamówienie</td>
<td>Odbiór zamówienia zwrotu</td>
<td>Zarejestruj przyjęcie ilości towaru, rejestrując numer autoryzacji zwrotu, a następnie utwórz pracę odłożenia dla innego pracownika.</td>
</tr>
<tr>
<td>Zwróć odebrane zamówienie i odłóż</td>
<td>Zarejestruj przyjęcie ilości towaru, rejestrując numer autoryzacji zwrotu, a następnie odłóż towary. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td rowspan="6">Zamówienie przeniesienia</td>
<td>Przyjmowanie pozycji z zamówienia przeniesienia</td>
<td>Zarejestruj przyjęcie ilości towaru, a następnie utwórz pracę odłożenia dla innego pracownika.

<strong>Uwaga:</strong> Użyj tej opcji tylko wtedy, gdy towary zostały wysłane z magazynu, który nie jest włączony dla procesów zarządzania magazynem.</td>
</tr>
<tr>
<td>Przyjmowanie i odkładanie pozycji z zamówienia przeniesienia</td>
<td>Zarejestruj przyjęcie ilości towaru i odłóż towary. Ten sam pracownik wykonuje oba działania.

<strong>Uwaga:</strong> Użyj tej opcji tylko wtedy, gdy towary zostały wysłane z magazynu, który nie jest włączony dla procesów zarządzania magazynem.</td>
</tr>
<tr>
<td>Przyjmowanie wiersza z zamówienia przeniesienia</td>
<td>Zarejestruj przyjęcie ilości towaru, a następnie utwórz pracę odłożenia dla innego pracownika.</td>
</tr>
<tr>
<td>Przyjęcie i odłożenie wiersza zamówienia przeniesienia</td>
<td>Zarejestruj przyjęcie ilości towaru i odłóż towary. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td>Przyjęcie numeru identyfikacyjnego</td>
<td>Odbierz przychodzące wcześniejsze powiadomienie o wysyłce (WPW) za pomocą numeru identyfikacyjnego.</td>
</tr>
<tr>
<td>Odbieranie numeru identyfikacyjnego i odłożenie</td>
<td>Odbierz i odłóż przychodzące wcześniejsze powiadomienie o wysyłce (WPW) za pomocą numeru identyfikacyjnego.</td>
</tr>
<tr>
<td rowspan="4">Produkcyjne</td>
<td>Zgłoszenie wyrobów gotowych</td>
<td>Zarejestruj ilość gotowego towaru, którzy został przygotowany do produkcji, i utwórz pracę odłożenia dla innego pracownika. Ilość może być częściową lub całą ilością planowaną dla produkcji.</td>
</tr>
<tr>
<td>Zgłoszenie i odłożenie wyrobów gotowych</td>
<td>Zarejestruj ilość gotowego towaru, którzy został przygotowany do produkcji, i odłóż towary. Ilość może być częściową lub całą ilością planowaną dla produkcji. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Wskazuje, że Kanban jest wypełniony i pozwala utworzyć pracę odłożenia dla innego pracownika.</td>
</tr>
<tr>
<td>Kanban odłożone</td>
<td>Wskazuje, że Kanban jest wypełniony i pozwala odłożyć towary. Ten sam pracownik wykonuje oba działania.</td>
</tr>
<tr>
<td rowspan="5">Zapasy</td>
<td>Przesunięcie</td>
<td>Rejestruje, że towary zostały przeniesione z jednej lokalizacji do innej. Pracownik określa lokalizację źródłową i docelową przenoszonych towarów.</td>
</tr>
<tr>
<td>Kwarantanna</td>
<td>Zmienia stan dostępnych zapasów dla numeru identyfikacyjnego lub lokalizacji, aby spowodować, że uszkodzone lub brakujące pozycje magazynowe są niedostępne.</td>
</tr>
<tr>
<td>Przeniesienie według szablonu</td>
<td>Przenosi towary z jednej lokalizacji do innej w sposób półautomatyczny. Pracownik wybiera lokalizację źródłową towarów i system używa dyrektywy lokalizacji do określenia lokalizacji docelowej.</td>
</tr>
<tr>
<td>Przeniesienie magazynu</td>
<td>Rejestruje, że towary zostały przesłane z jednego magazynu do innego. Wymaga to, żeby pracownik miał uprawnienia wykonywania pracy w obu magazynach.

<strong>Uwaga:</strong> Ta pozycja menu wymaga domyślnego arkusza przeniesień magazynowych z wybranym ustawieniem <strong>Księgowanie</strong> dla pola <strong>Losowanie załącznika</strong>.</td>
</tr>
<tr>
<td>Ładowanie numeru identyfikacyjnego</td>
<td>Użyj tej opcji podczas konfigurowania magazynu po raz pierwszy. Zeskanuje wszystkie numery identyfikacyjne we wszystkich lokalizacjach w magazynie. Lokalizacje muszą być kontrolowane za pomocą numerów identyfikacyjnych. Tej opcji nie można użyć, jeśli <strong>Numer seryjny</strong> lub <strong>Numer partii</strong> są wymienione powyżej pozycji <strong>Lokalizacja</strong> w hierarchii rezerwacji zapasów.</td>
</tr>
<tr>
<td rowspan="3">Liczba cykli</td>
<td>Korekta wewnętrzna</td>
<td>Zwiększ ilość towarów w zapasach. Określ lokalizację, numer identyfikacyjny, towar, ilość, jednostkę miary i stan.</td>
</tr>
<tr>
<td>Korekta zewnętrzna</td>
<td>Zmniejsz ilość towarów w zapasach. Określ lokalizację, numer identyfikacyjny, towar, ilość, jednostkę miary i stan zapasu.</td>
</tr>
<tr>
<td>Inwentaryzacja ciągła punktowa</td>
<td>Rozpocznij zliczanie dla lokalizacji. Pracownik musi zliczyć wszystkie towary w danej lokalizacji. Jeśli wynik inwentaryzacji jest mniejszy od oczekiwanego, brakująca ilość jest uznawana za stratę.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Konfigurowanie elementów menu do przetwarzania istniejącej pracy
Oprócz zdefiniowania elementów to utworzenia pracy magazynu, można ustawić pozycje menu do przetwarzania pracy, która została już utworzona. Ustaw pole **Tryb** na wartość **Praca** i wybierz opcję **Użyj istniejącej pracy**. Na karcie **Ogólne** pojawi się kilka dodatkowych opcji. Można kontrolować dostęp do elementu menu przez przypisywanie do nich klas pracy na skróconej karcie **Klasa pracy**. Klasy pracy definiują pracę, którą element menu może przetworzyć. Klasa pracy może również być używana do udzielania dostępu rolom właściwym dla użytkownika lub oddzielnego przetwarzania różnych typów operacji. W poniższej tabeli przedstawiono dostępne opcje. Opcję można wybrać w polu **Sterowane przez** na stronie **Elementy menu urządzenia przenośnego**. 

<table>




<thead>
<tr class="header">
<th>Opcja</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Brak</td>
<td>Ta wartość domyślna nie przetwarza pracy.</td>
</tr>
<tr class="even">
<td>Sterowane przez system</td>
<td>Supply Chain Management określa rodzaj pracy, która jest przypisana do pracownika, i kolejność, w jakiej pracownik wykonuje pracę. Po wybraniu tej opcji można wybrać opcję <strong>Praca sterowana przez system</strong> w okienku akcji, aby otworzyć stronę <strong>Kolejność sortowania określona przez system</strong>, na której można ustawić kryteria sortowania dla pracy. Kryteria sortowania określają porządek wykonywania pracy przez pracownika. Można dodać dowolną liczbę kryteriów zależnie od potrzeb.</td>
</tr>
<tr class="odd">
<td>Sterowane przez użytkownika</td>
<td>Pracownik wybiera pracę do wykonania oraz kolejność, w której należy ją wykonać.</td>
</tr>
<tr class="even">
<td>Grupowanie użytkowników</td>
<td>Pracownik ręcznie grupuje pracę. Ta opcja przydaje się na przykład wtedy, gdy pracownik może jednocześnie odebrać wiele towarów w lokalizacji. Po zakończeniu odbioru wszystkich wymaganych towarów pracownik może odłożyć te towary.</td>
</tr>
<tr class="odd">
<td>Grupowanie systemowe</td>
<td>Supply Chain Management grupuje pracę dla pracownika na podstawie określonego pola. Na przykład praca pobierania jest grupowana gdy pracownik skanuje identyfikator wysyłki, identyfikator ładunku lub dowolną wartość, którą można połączyć z poszczególnymi jednostkami pracy. Jeśli wybierzesz tę opcję, wymagane są następujące pola:
<ul>
<li><strong>Pole grup systemowych</strong> — wybierz pole, które pracownik musi przeskanować w celu pogrupowania pracy.</li>
<li><strong>Etykieta grup systemowych</strong> — wpisz tekst informujący pracownika o tym, co należy zeskanować w celu pogrupowania pracy.</li>
</ul></td>
</tr>
<tr class="even">
<td>Zweryfikowany użytkownik skierowany</td>
<td>Pracownik wybiera pracę do wykonania, gdy praca jest skojarzona z większą jednostką, np. ładunkiem lub wysyłką. Pracownik określa kolejność, w jakiej towary są pobierane. Jeśli wybierzesz tę opcję, wymagane są następujące pola:
<ul>
<li><strong>Pole zweryfikowanego użytkownika skierowanego</strong> — wybierz pole, które pracownik musi przeskanować w celu pogrupowania pracy.</li>
<li><strong>Etykieta zweryfikowanego użytkownika skierowanego</strong> — tekst informujący pracownika o tym, co należy zeskanować, gdy praca odbierania jest pogrupowana przez system.</li>
</ul>
Ta opcja przydaje się na przykład wtedy, gdy wiele palet jest przygotowanych do załadunku. Jeśli wybierzesz <strong>LoadId</strong> w polu <strong>Zweryfikowany użytkownik skierowany</strong>, pracownik może odebrać dowolną paletę skojarzoną z ładunkiem. Jeśli pracownik zeskanuje towar, który nie jest skojarzony z ładunkiem, wyświetlany jest komunikat o błędzie.</td>
</tr>
<tr class="odd">
<td>Wybór grupy</td>
<td>Pracownik grupuje pracę w grupy. Grupy pozwalają pracownikom wybierać towary z jednej lokalizacji dla wielu zamówień pracy jednocześnie.</td>
</tr>
<tr class="even">
<td>Grupowanie inwentaryzacji ciągłej</td>
<td>Pracownik wybiera strefę, pulę pracy lub lokalizację, a Supply Chain Management przypisuje pracę na podstawie wyboru. Jeśli wybierzesz tę opcję, możesz też kliknąć <strong>Inwentaryzacja ciągła</strong> w okienku akcji, aby określić dodatkowe informacje do wyświetlenia i możesz też określić, ile razy pracownik musi potworzyć zliczanie, jeśli wystąpi rozbieżność.</td>
</tr>
 <tr class="odd">
<td>Ładowanie transportu</td>
<td>Ta funkcja umożliwia kilku pracownikom magazynu ładowanie zapasów z tego samego lub różnych ładunków na tę samą ciężarówkę, gdzie ładunki są wysłane w całości lub częściowo.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Dodatkowe opcje elementów menu
Dodatkowe elementy menu są dostępne na stronie **Elementy menu urządzenia przenośnego**. Dostępne opcje zależą od procesu, dla którego elementu menu jest konfigurowany. 

W poniższej tabeli opisano te opcje.

<table>




<thead>
<tr class="header">
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zezwalaj na dzielenie pracy</td>
<td>Wybranie tej opcji pozwala użytkownikom przydzielać dla zleceń do kilku numerów identyfikacyjnych. Przydaje się to na przykład, gdy docelowy numer identyfikacyjny jest pełny, a pracownik musi przypisać pozostałe towary do innego numeru identyfikacyjnego. Pracownik może wybrać opcję <strong>Pełny</strong>, by określić, że dany numer identyfikacyjny jest pełny, i zatrzymać dla niego pracę odbierania. Wyświetlana jest wtedy lokalizacja odłożenia dla odebranych towarów, a praca odebrania, która została ukończona, jest przenoszona do nowego zlecenia. Pozostała praca odbioru dla docelowego numeru identyfikacyjnego pozostaje w oryginalnym zleceniu.</td>
</tr>
<tr class="even">
<td>Kotwiczenie</td>
<td>Zaznaczenie tej opcji pozwala pracownikom określić lokalizację, która zastąpi sugerowaną lokalizację pośrednią lub załadunku. Cała pozostała praca odkładania jest kierowana do nowej lokalizacji. Na przykład to jest przydatne, gdy pracownik ma odłożyć towary dla zamówienia 1 w lokalizacji pośredniej przy Doku 1, ale nie może, bo poprzedni ładunek nie wyszedł jeszcze z lokalizacji. Zamiast czekać na to, aż lokalizacja pośrednia przy Doku 1 będzie dostępna, pracownik decyduje się użyć lokalizacji pośredniej przy Doku 2. W tym przypadku pracownik zastępuje sugerowaną lokalizację pośrednią. Lokalizacja odłożenia dla wszystkich pozostałych towarów w zleceniu jest aktualizowana na lokalizację pośrednią przy Doku 2. W przypadku wybrania tej opcji należy ustawić pole <strong>Kotwicz wg</strong>.</td>
</tr>
<tr class="odd">
<td>Kotwicz wg</td>
<td>Jeśli używasz kotwiczenia, musisz określić, czy ma to być kotwiczenie według wysyłki czy według ładunku.</td>
</tr>
<tr class="even">
<td>Identyfikator szablon inspekcji</td>
<td>Wybierz szablon inspekcji pracy, który przerwie proces pracy dla tego elementu menu, żeby umożliwić wykonanie innej operacji. Na przykład jeśli dane element menu dotyczy pracy przychodzącej, szablon inspekcji może wymagać, by pracownik sprawdził temperaturę w kontenerze dostawy. Punkt przerwania procesu jest określony w szablonie inspekcji. Ten punkt może być na przykład w chwili rozpoczęcia lub ukończenia pracy, albo w momencie zmiany jej stanu.</td>
</tr>
<tr class="odd">
<td>Identyfikator profilu grupy</td>
<td>Wybierz profil grupy, który ma być użyty do wyboru grupy. Profil grupy zawiera ustawienia takie jak to, czy grupa ma być tworzona automatycznie, nazwy stanowisk i liczba jednostek pracy, które mogą być do nich przypisane, kiedy dzielić grupy na pojedyncze jednostki oraz czy konieczna jest weryfikacja. To pole jest dostępne tylko wtedy, gdy pole <strong>Sterowane przez</strong> ma wartość <strong>Wybór grupy</strong>.</td>
</tr>
<tr class="even">
<td>Najpierw zliczaj łączną ilość pozycji</td>
<td>Wybierz tę opcję, aby przed zliczeniem pracownik musiał policzyć ilość całkowitą. W przypadku rozbieżności pracownik musi podać dodatkowe informacje, takie jak numer identyfikacyjny, numer partii i numer seryjny.</td>
</tr>
<tr class="odd">
<td>Utwórz przeniesienie</td>
<td>Zaznacz tę opcję, aby umożliwiać pracownikowi tworzenie pracy dla przenoszenia bez konieczności wykonania pracy natychmiast. Jest to przydatne, na przykład jeśli przeprowadzono inspekcję jakości i inspektor chce przenieść towar z obszaru kontroli jakości.</td>
</tr>
<tr class="even">
<td>Kod dyrektywy</td>
<td>Aby użyć określonej dyrektywy lokalizacji, wybierz kod dyrektywy skojarzony z dyrektywą lokalizacji. To pole jest dostępne, kiedy tworzysz pracę, a procesem tworzenia pracy jest <strong>Przeniesienie według szablonu</strong>.</td>
</tr>
<tr class="odd">
<td>Wyłącz progi inwentaryzacji ciągłej</td>
<td>Zaznacz tę opcję, aby zignorować próg zliczania cykli. Jeśli wybierzesz tę opcję, praca cyklu zliczenie nie jest tworzona po przekroczeniu wartości progowej.</td>
</tr>
<tr class="even">
<td>Wyświetl kod dyspozycji partii</td>
<td>Zaznacz to pole wyboru, aby wyświetlić kody dyspozycji partii. Na przykład możesz wyświetlić kody dyspozycji partii, gdy odbierzesz zwróconą partię. Pracownicy mogą oceniać stanu lub jakości partii oraz wybranie odpowiedniego kodu. Reguły dotyczące kodu dyspozycji partii określają, czy partia będzie dostępna dla innych procesów magazynu. Jeśli nie zaznaczysz tej opcji używany jest jeden z następujących kodów dyspozycji partii:
<ul>
<li>Jeśli otrzymasz nowy numer partii, używany jest domyślny kod dyspozycji partii określony w grupie modeli towarów.</li>
<li>Kod dyspozycji partii jest już przypisany do używanej partii.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wyświetl kod dyspozycji</td>
<td>Zaznacz to pole wyboru, aby wyświetlić kody dyspozycji. Na przykład możesz wyświetlić kody dyspozycji, gdy odbierzesz zwrócone towary. Pracownicy mogą oceniać stanu lub jakości towarów oraz wybranie odpowiedniego kodu. Reguły dotyczące kodu dyspozycji określają, czy towary będą dostępne dla innych procesów magazynu.</td>
</tr>
<tr class="even">
<td>Wyświetl kolumnę Stan zapasów</td>
<td>Zaznaczenie tej opcji spowoduje wyświetlanie stanu towarów w zapasach. Ta opcja jest dostępna dla wszystkich elementów menu używających istniejącej pracy, poza inwentaryzacją ciągłą.</td>
</tr>
<tr class="odd">
<td>Wyświetl podsumowanie ekranu pobrania</td>
<td>Zaznacz tę opcję, aby wyświetlić podsumowanie pracy odbierania dla wybranego zlecenia. Podsumowanie jest wyświetlane do momentu przetworzenia pierwszego wiersza pracy dla zlecenia.</td>
</tr>
<tr class="even">
<td>Generuj numer identyfikacyjny</td>
<td>Zaznacz tę opcję, aby wygenerować unikalny numer identyfikacyjny na podstawie wybranej sekwencji numerów. Na przykład można wygenerować numer identyfikacyjny dla towarów otrzymanych dla zamówień zakupu.</td>
</tr>
<tr class="odd">
<td>Grupuj odłożone</td>
<td>Zaznaczenie tej opcji powoduje pogrupowanie pracy odłożenia. Ta opcja jest dostępna, gdy praca została pogrupowana według pracownika lub przez Supply Chain Management. Gdy pracownik zakończy wszystkie prace pobrania w grupie zostanie dla niej utworzona praca odłożenia.</td>
</tr>
<tr class="even">
<td>Typy korekt zapasów </td>
<td>Wybierz typ korekty zapasów, który określa arkusz inwentaryzacji zapasów używany do zaksięgowania korekty oraz, czy usunąć rezerwacje. To pole jest dostępne tylko dla procesów tworzenia pracy <strong>Korekta wewnętrzna</strong> i <strong>Korekta zewnętrzna</strong>.</td>
</tr>
<tr class="odd">
<td>Zastąp numer partii</td>
<td>Zaznaczenie tej opcji umożliwia pracownikom, którzy zgłaszają wyroby gotowe dla zlecenia produkcyjnego wprowadzenie numeru partii, który różni się od numeru partii przypisanego do zlecenia produkcyjnego.</td>
</tr>
<tr class="even">
<td>Zastąp docelowy numer identyfikacyjny</td>
<td>Zaznaczenie tej opcji umożliwia pracownikom określenie docelowego numeru identyfikacyjnego, który różni się od sugerowanego docelowego numeru identyfikacyjnego. Użyj tej opcji, gdy pierwsze pobranie w ramach zlecenia obejmuje całą ilość pozycji w numerze identyfikacyjnym. Jest to przydatne np. przy ponownym wykorzystaniu palety.</td>
</tr>
<tr class="odd">
<td>Pobierz i zapakuj</td>
<td>Wybranie tej opcji umożliwia pracownikom połączenie pracy dla zamówienia sprzedaży lub ładunku w jedną jednostkę roboczą. Pracownika może wykonać pracę tylko dla zamówienia sprzedaży lub ładunku. Ta opcja jest przydatna, np. kiedy trzeba zwiększyć ilość w zamówieniu sprzedaży po utworzeniu ładunku, wysyłki i pracy dla zamówienia sprzedaży. Ta opcja jest dostępna, gdy element menu używa istniejącej pracy i praca jest sterowana przez system lub użytkownika.</td>
</tr>
<tr class="even">
<td>Pobierz z najstarszej partii</td>
<td>Wskazuje, czy pracownik musi najpierw pobrać w lokalizacji najstarszą partię. Dostępne są następujące opcje:
<ul>
<li><strong>Brak</strong> — pracownik może pobrać dowolną partię w lokalizacji. Pracownik nie otrzymuje żadnej wiadomości.</li>
<li><strong>Ostrzeżenie</strong> — pracownik może odebrać dowolną partię w lokalizacji, ale otrzyma ostrzeżenie, jeśli pobierze partię, która nie jest najstarsza.</li>
<li><strong>Wymuszaj</strong>— pracownik musi pobrać najstarszą partię w lokalizacji. Jeśli partie nie jest najstarszą partią, wyświetla się komunikat o błędzie. <strong>Uwaga:</strong> Ta opcja jest stosowana tylko wtedy, gdy <strong>Numer partii</strong> jest niższy niż <strong>Lokalizacja</strong> w hierarchii rezerwacji przypisanej do towaru.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Drukuj etykietę</td>
<td>Zaznaczenie tej opcji umożliwia pracownikom drukowanie etykiet numerów identyfikacyjnych.</td>
</tr>
<tr class="even">
<td>Pole grup systemowych</td>
<td>Wybierz pole określające, jak Supply Chain Management pogrupuje pracę pobrania dla pracownika. Na przykład, jeśli wybierzesz pole <strong>ShipmentId</strong>, pracownik będzie skanować identyfikator wysyłki w celu pogrupowania pracy pobrania. Wszystkie prace dla wysyłki są następnie przypisywane do pracownika. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Trzeba też wprowadzić tekst w polu <strong>Etykieta grup systemowych</strong>, informujący pracownika o tym, co należy zeskanować.</td>
</tr>
<tr class="odd">
<td>Etykieta grup systemowych</td>
<td>Wpisz tekst informujący pracownika o tym, co należy zeskanować, gdy praca odbierania jest pogrupowana przez Supply Chain Management. Na przykład, jeśli używasz pola <strong>ShipmentId</strong> do grupowania pracy pobrania według wysyłki, możesz wprowadzić <strong>Shipment ID</strong> w polu. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Musisz także wybrać pole, według którego będzie przeprowadzane grupowanie w polu <strong>Grupowanie systemowe</strong>.</td>
</tr>
<tr class="even">
<td>Użyj danych domyślnych</td>
<td>Wybranie tej opcji umożliwia włączenie przycisku <strong>Dane domyślne</strong> w okienku akcji, gdzie można wybrać pola wyświetlające dane, które są najbardziej potrzebne pracownikowi. Ta opcja jest użyteczna, np. gdy pracownik często pobiera towar z tej samej lokalizacji. Można wybrać pole <strong>Lokalizacja początkowa</strong>, aby wyświetlić lokalizację domyślną.</td>
</tr>
<tr class="odd">
<td>Pole zweryfikowanego użytkownika skierowanego</td>
<td>Wybierz pole, które pracownik musi przeskanować w celu pogrupowania pracy. Na przykład, jeśli wybierzesz <strong>LoadId</strong>, pracownik może pobrać dowolną pracę skojarzoną z wybranym ładunkiem. Trzeba też wprowadzić tekst w polu <strong>Etykieta zweryfikowanego użytkownika skierowanego</strong>, informujący pracownika o tym, co należy zeskanować.</td>
</tr>
<tr class="even">
<td>Etykieta zweryfikowanego użytkownika skierowanego</td>
<td>Wpisz tekst informujący pracownika o tym, co należy zeskanować, gdy praca odbierania jest pogrupowana przez pole zweryfikowanego użytkownika skierowanego. Na przykład, jeśli używasz pola <strong>LoadId</strong> do grupowania pracy pobrania dla ładunku, możesz wprowadzić <strong>Load ID</strong> w polu.</td>
</tr>
<tr class="odd">
<td>Kod szablonu pracy</td>
<td>Wybierz szablon pracy, który utworzy pracę dla procesu. Na przykład jeśli otrzymujesz towar dla zamówienia zakupu, praca odłożenia zostanie wygenerowana na podstawie szablonu pracy. Jeśli nie wybierzesz szablonu pracy, Supply Chain Management przypisze szablon na podstawie kryteriów kwerendy. Aby uzyskać więcej informacji dotyczących szablonów pracy, zobacz <a href="control-warehouse-location-directives.md">Kontrolowanie pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji</a>.</td>
<tr class="even">
<td>Pokaż listę wierszy pracy</td>
<td>Umożliwia wybranie opcji wyświetlania pracowników i interakcji z wierszami aktualnie wybranej pracy pobrania. Aby uzyskać więcej informacji dotyczących tej opcji, zapoznaj się z tematem <a href="pick-line-overview.md">Konfigurowanie elementu menu urządzenia przenośnego w celu dostarczenia przeglądu wiersza pobrania</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Wymagaj od pracowników potwierdzenia produktów, lokalizacji lub ilości podczas pobierania pozycji

Można skonfigurować potwierdzenia pracy, które wymagają od pracownika użycia urządzenia mobilnego w celu zarejestrowania lokalizacji lub ilości podczas wykonywania pracy w magazynie. Potwierdzenia pracy pomagają zapewnić, że pracownik jest w prawidłowym miejscu lub obsługuje poprawne ilości towarów. Można także włączyć Supply Chain Management do automatycznego potwierdzenia rejestracji pracownika. Po włączeniu automatycznego potwierdzenia nie można jednocześnie wymagać potwierdzeń dla lokalizacji lub ilości. Potwierdzenia pracy zawierają także produkty i warianty produktu. Ponadto można zarejestrować potwierdzenia przez skanowanie kodu kreskowego. Aby potwierdzić produkty i warianty produktów, trzeba wprowadzić identyfikator produktu/wariantu produktu. Może to być identyfikator produktu, identyfikator wyszukiwania produktu, identyfikator zewnętrzny, GTIN lub kod kreskowy. Po wprowadzeniu identyfikatora lub zeskanowaniu kodu kreskowego wymiary wariantu produktu są wyświetlane w urządzeniu przenośnym. 

W poniższej tabeli przedstawiono różne typy pracy, z którymi można używać potwierdzenia pracy.

| Opcja | Opis |
|------------------------|----------------------------------------------------------------------------|
| Pobierz | Żądaj potwierdzenia podczas pobierania towaru. |
| Odłożenie | Żądaj potwierdzenia podczas umieszczania towarów w lokalizacji. |
| Inwentaryzacja | Żądaj potwierdzenia podczas inwentaryzacji ciągłej. |
| Korekty | Żądaj potwierdzenia podczas korygowania ilości zapasów. |
| Niestandardowy | Żądaj potwierdzenia dla niestandardowej pracy. |
| Kwarantanna | Żądaj potwierdzenia podczas przenoszenia towarów do kwarantanny. |
| Tworzenie numeru identyfikacyjnego | Żądaj potwierdzenia podczas konsolidacji towarów do zbudowania numeru identyfikacyjnego. |
| Drukuj | Żądaj potwierdzenia podczas drukowania etykiet numeru identyfikacyjnego. |
| Zmiana stanu | Żądaj potwierdzenia podczas zmiany stanu zapasów. |

> [!NOTE]
> Możesz jedynie wymagać potwierdzenia produktu dla prac typu pobieranie i odkładanie.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy typu Zamówienie zakupu](tasks/set-up-mobile-device-menu.md)
- [Konfigurowanie elementu menu urządzenia przenośnego do rejestrowania towarów przyjętych](tasks/set-up-mobile-device-menu-item-register-received-items.md)
- [Stany zapasów](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Zadania importowania i eksportowania danych
description: "Obszar roboczy Zarządzanie danymi umożliwia tworzenie zadań importu i eksportu danych oraz zarządzanie nimi."
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: d58bab48c65bb891155af95c79738b019e5760bf
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="data-import-and-export-jobs"></a>Zadania importowania i eksportowania danych

[!include [banner](../includes/banner.md)]

Aby tworzyć zadania importu i eksportu w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations i zarządzać nimi, należy korzystać z obszaru roboczego **Zarządzanie danymi**. Domyślne proces importowania i eksportowania danych tworzy tabelę przemieszczania dla każdej jednostki w docelowej bazie danych. Tabele tymczasowe umożliwiają sprawdzenie, czyszczenie lub konwersję danych przed ich przeniesieniem.

> [!NOTE]
> W tym temacie założono, że znasz koncepcję [jednostek danych](data-entities.md).

## <a name="data-importexport-process"></a>Proces importu/eksportu danych
Poniżej przedstawiono kroki importowania lub eksportowania danych.

1. Utwórz zadanie importu lub eksportu, w którym należy wykonać następujące zadania:

    - Zdefiniuj kategorię projektu.
    - Zdefiniuj jednostki do zaimportowania lub wyeksportowania.
    - Ustaw format danych zadania.
    - Określ kolejność jednostek tak, aby były przetwarzane w grupach logicznych oraz w kolejności, która ma sens.
    - Określ, czy mają być używane tabele przemieszczania.

2. Sprawdź, czy dane źródłowe i dane docelowe są prawidłowo zmapowane.
3. Sprawdź zabezpieczenia zadania importu lub eksportu.
4. Uruchom zadanie importu lub eksportu.
5. Sprawdź, czy zadanie zostało wykonane zgodnie oczekiwaniami, przeglądając historię zadań.
6. Wyczyść tabele przemieszczania.

Pozostałe sekcje tego tematu zawierają szczegółowe informacje o każdym kroku procesu.

> [!NOTE]
> Aby odświeżyć formularz importu/eksportu danych i zobaczyć aktualny postęp, użyj ikony odświeżania formularza. Nie zalecamy odświeżania na poziomie przeglądarki, ponieważ spowoduje to przerwanie wszystkich zadań importu/eksportu, które nie są wykonywane wsadowo.

## <a name="create-an-import-or-export-job"></a>Tworzenie zadania importu lub eksportu
Zadanie importu lub eksportu danych może zostać uruchomione raz lub wiele razy.

### <a name="define-the-project-category"></a>Definiowanie kategorii projektu
Zalecamy, aby poświęcić czas na wybranie odpowiedniej kategorii projektu dla zadania importu lub eksportu. Kategorie projektu ułatwiają zarządzanie powiązanymi zadaniami.

### <a name="identify-the-entities-to-import-or-export"></a>Zdefiniowanie jednostki do zaimportowania lub wyeksportowania
Do zadania importu lub eksportu można dodać określone jednostki lub wybrać szablon do zastosowania. Szablony umożliwiają wypełnienie zadania listą jednostek. Opcja **Zastosuj szablon** jest dostępna po nadaniu zadaniu nazwy i jego zapisaniu.

### <a name="set-the-data-format-for-the-job"></a>Ustawianie formatu danych zadania
Podczas wybieranie jednostki należy wybrać format eksportowanych lub importowanych danych. Formaty można określić, używając kafelka **Ustawienia źródeł danych**. Format danych źródłowych jest kombinacją elementów **Typ**, **Format pliku**, **Separator wiersza** i **Separator kolumny**. Istnieją również inne atrybuty, ale to są główne, które należy znać. Poniższa tabela zawiera listę prawidłowych kombinacji.

| **Format pliku**        | **Separator wiersza/kolumny**                   | **Styl XML**             |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-Nie dotyczy-                     |
| Plik XML                    | \-Nie dotyczy-                                      | Element XML Atrybut XML |
| Ograniczone, stała szerokość | Przecinek, średnik, tabulator, pionowa kreska, dwukropek | \-Nie dotyczy-                     |



### <a name="sequence-the-entities"></a>Określanie kolejności jednostek
Kolejność jednostek można określić w szablonie danych albo w zadaniach importu lub eksportu. Po uruchomieniu zadania, które zawiera więcej niż jedną jednostkę należy się upewnić, że kolejność jednostek danych jest prawidłowa. Kolejność jednostek określa się głównie po to, aby obsłużyły zależności funkcjonalne między jednostkami. Jeżeli jednostki nie mają żadnych zależności funkcjonalnych, można zaplanować ich import lub eksport równoległy.

#### <a name="execution-units-levels-and-sequences"></a>Jednostki wykonywania, poziomy i kolejności
Jednostka wykonywania, poziom w jednostce wykonywania i kolejność jednostek ułatwiają kontrolowanie jakości eksportu lub importu danych.

- Jednostki w różnych jednostkach wykonywania są przetwarzane równolegle.
- W każdej jednostce wykonywania jednostek są przetwarzane równolegle, jeśli mają ten sam poziom.
- Na każdym poziomie jednostki są przetwarzane zgodnie z ich kolejnym numerem na tym poziomie.
- Po przetworzeniu jednego poziomu przetwarzany jest następny.

#### <a name="resequencing"></a>Zmiana kolejności
Zmiana kolejności jednostek może być konieczna w następujących sytuacjach:

- Jeżeli dla wszystkich zmian używane jest tylko jedno zadanie danych, można użyć opcji zmiany kolejności w celu optymalizacji czasu wykonania pełnego zadania. W takich przypadkach można użyć jednostki wykonywania do reprezentacji modułu, poziomu do reprezentacji obszaru funkcji w module, a kolejności do reprezentacji jednostki. Używając tej metody można pracować równolegle między modułami, ale także pracować kolejno w module. Aby zapewnić powodzenie operacji równoległych, należy uwzględnić wszystkie zależności.
- W przypadku używania wielu zadań danych (na przykład jednego zadania dla każdego modułu) można użyć harmonogramu w celu określenia poziomu i kolejności jednostek i optymalnego wykonania.
- Jeżeli nie ma żadnych zależności, można określić kolejność jednostek w różnych jednostkach wykonywania w celu maksymalnej optymalizacji.

Menu **Zmiana kolejności** jest dostępne po wybraniu wielu jednostek. Kolejność można zmienić na podstawie opcji jednostki wykonywania, poziomu lub kolejności. Można ustawić przyrost w celu zmiany kolejności wybranych jednostek. Numer jednostki, poziomu i/lub kolejności wybrany dla każdej jednostki zostanie zaktualizowany o określony przyrost.

#### <a name="sorting"></a>Sortowanie
Można użyć opcji **Sortuj według**, aby wyświetlić listę jednostek w odpowiedniej kolejności.

### <a name="truncating"></a>Obcięcie
W projektach importowania można wybrać opcję obcinania rekordów w jednostek przed rozpoczęciem importu. Jest to przydatne, jeśli rekordy muszą zostać zaimportowane do czystego zestawu tabel. To ustawienie jest domyślnie wyłączone.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Sprawdzanie, czy dane źródłowe i dane docelowe są prawidłowo zmapowane
Mapowanie to funkcja dotycząca zadań importu i eksportu.

- W kontekście zadania importu mapowanie opisuje, które kolumny w pliku źródłowych będą kolumnami w tabeli przemieszczania. Dlatego system może określić, które dane z kolumny w pliku źródłowym muszą zostać skopiowane do kolumny w tabeli przemieszczania.
- W kontekście zadania eksportu mapowanie opisuje, które kolumny w tabeli przemieszczanie (czyli w źródle) będą kolumnami w pliku docelowym.

Jeżeli nazwy kolumn w tabeli przemieszczania oraz w pliku są zgodne, system automatycznie określa mapowanie na podstawie nazw. Jeżeli jednak nazwy różnią się, kolumny nie są mapowane automatycznie. W tych przypadkach należy uzupełnić mapowanie, wybierając opcję **Wyświetl mapę** dla jednostki w zadaniu danych.

Dostępne są dwa widoki mapowania: **Wizualizacja mapowania**, czyli widok domyślny i **Szczegóły mapowania**. Czerwona gwiazdka (\*) określa pola wymagane pola w jednostce. Te pola muszą zostać zmapowane przed rozpoczęciem pracy z jednostką. Podczas pracy z jednostką można anulować mapowanie innych pól. Aby anulować mapowanie pola, wybierz pole w kolumnie **Jednostka** lub kolumnie **Źródło**, a następnie wybierz opcję **Usuń wybór**. Wybierz opcję **Zapisz**, aby zapisać zmiany, a następnie zamknij stronę, aby wrócić do projektu. Ten sam proces umożliwia edycję mapowania pól od źródła do przemieszczania po ukończeniu importu.

Mapowanie można wygenerować na stronie, wybierając opcję **Generuj mapowanie źródła**. Wygenerowane mapowanie zachowuje się jak mapowanie automatyczne. Dlatego należy ręczne zmapować wszystkie niezmapowane pola.

![Mapowanie danych](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Sprawdzanie zabezpieczeń zadania importu lub eksportu
Dostęp do obszaru roboczego **Zarządzanie danymi** można ograniczyć tak, aby użytkownicy inni niż administratorzy mieli dostęp tylko do określonych zadań danych. Dostęp do zadania danych oznacza pełny dostęp do historii wykonania tego zdania i dostęp do tabeli przemieszczania. W związku z tym należy się upewnić, że kontrola dostępu odpowiednie obowiązują podczas tworzenia zadania danych.

### <a name="secure-a-job-by-roles-and-users"></a>Zabezpieczanie zadania według ról i użytkowników
Skorzystaj z menu **Odpowiednie role**, aby ograniczyć zadanie do jeden lub kilku ról zabezpieczeń. Dostęp do tego zadania będą mieli tylko użytkownicy o tych rolach.

Zadanie można także ograniczyć do określonych użytkowników. Zabezpieczenie zadania według użytkowników zamiast według ról ułatwia określenie, czy wielu użytkowników jest przypisanych do roli.

### <a name="secure-a-job-by-legal-entity"></a>Zabezpieczanie zadania według firm
Zadania danych mają charakter globalny. Dlatego, jeżeli zadanie danych zostało utworzone i użyte w firmie, będzie widoczne w innych firmach w systemie. To domyślne zachowanie może być preferowane w niektórych scenariuszach aplikacji. Przykładowo organizacja, która importuje faktury za pomocą jednostek danych może korzystać z centralnego zespołu przetwarzania faktur odpowiedzialnego za zarządzanie błędami w fakturach we wszystkich oddziałach organizacji. W tym scenariuszy przydatny dla centralnego zespołu przetwarzania faktur jest dostęp do zadań importu faktur ze wszystkich firm. Dlatego zachowanie domyślne spełnia wymagania z punktu widzenia firmy.

Jednak w organizacji może być preferowane posiadanie zespołu przetwarzania faktur w każdej firmie. W takim przypadku zespół w firmie powinien mieć dostęp tylko do zadania importu faktur we własnej firmie. W celu spełnienia tego wymagania można skonfigurować kontrolę dostępu do zadań danych na podstawie firmy, używając menu **Odpowiednie firmy** w zadaniu danych. Po ukończeniu konfiguracji użytkownicy widzą tylko te zadania, które są dostępne w firmie, w której są aktualnie zalogowani. Aby zobaczyć zadania z innej firmy, użytkownicy muszą przełączyć się na tę firmę.

Zadanie można jednocześnie zabezpieczyć według ról, użytkowników i firm.

## <a name="run-the-import-or-export-job"></a>Uruchamianie zadania importu lub eksportu
Zadanie można uruchomić jeden raz, klikając przycisk **Importuj** lub **Eksportuj** po zdefiniowaniu zadania. Aby skonfigurować zadanie cykliczne, wybierz opcję **Utwórz cykliczne zadanie danych**.

## <a name="validate-that-the-job-ran-as-expected"></a>Sprawdzanie, czy zadanie zostało uruchomione zgodnie z oczekiwaniami
Dostępna jest historia zadań umożliwiająca rozwiązywanie problemów i badanie zadań importu i eksportu. Historyczne uruchomienia zadań są zorganizowane według zakresów czasu.

![Zakresy historii zadań](./media/dixf-job-history.md.png)

Dla każdego uruchomionego zadania dostępne są następujące informacje:

- Szczegóły wykonania
- Dziennik wykonywania

Szczegóły wykonania pokazują stan każdej jednostki danych przetworzonych przez zadanie. Dlatego można szybko znaleźć następujące informacje:

- Które jednostki zostały przetworzone
- Ile rekordów zostało pomyślnie przetworzonych, a przetworzenie ilu nie powiodło się dla każdej jednostki
- Rekordy przemieszczania dla każdej jednostki

Dane przemieszczania można pobrać w pliku dla zadań eksportu lub pobrać je jako pakiet dla zadań importu i eksportu.

W oknie szczegółów wykonania można także otworzyć dziennik wykonania.

## <a name="clean-up-the-staging-tables"></a>Czyszczenie tabel przemieszczania
Tabele przemieszczania można wyczyścić, używając funkcji **Czyszczenie przemieszczania###** w obszarze roboczym **Zarządzanie danymi**. Następujących opcji można użyć, aby wybrać, które rekordy mają zostać usunięte z danej tabeli przemieszczania:

- **Jednostka** — jeżeli dostępna jest tylko jednostka, wszystkie rekordy z tabeli przemieszczania tej jednostki są usuwane. Wybierz tę opcję, aby wyczyścić wszystkie dane dla jednostki we wszystkich projektach danych i wszystkich zadaniach.
- **Identyfikator zadania** — jeżeli dostępny jest tylko identyfikator zadania, wszystkie rekordy dla wszystkich jednostek w wybranym zadaniu są usuwane z odpowiednich tabel przemieszczania.
- **Projekty danych** — jeżeli wybrano tylko projekt danych, wszystkie rekordy dla wszystkich obiektów oraz we wszystkich zadaniach dla wybranego projektu danych są usuwane.

Można także połączyć opcje, aby dodatkowo ograniczyć usuwany zestaw rekordów.


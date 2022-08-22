---
title: Dostosowywanie tytułów kroków i instrukcji dla aplikacji mobilnej Warehouse Management
description: W tym artykule opisano sposób tworzenia i pokazywania niestandardowych instrukcji wykonywania poszczególnych kroków przepływów zadania konfigurowanych dla aplikacji mobilnej Warehouse Management.
author: Mirzaab
ms.date: 08/11/2021
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 40b2115126aae28a41feaec4d3aabd73595107cd
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220158"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Dostosowywanie tytułów kroków i instrukcji dla aplikacji mobilnej Warehouse Management

> [!IMPORTANT]
> Funkcje opisane w tym artykule dotyczą tylko nowej aplikacji mobilnej Warehouse Management. Nie wpływają one na starą aplikację magazynu, która jest obecnie przestarzała.

W tym artykule opisano sposób tworzenia i pokazywania niestandardowych instrukcji wykonywania poszczególnych kroków poszczególnych przepływów zadania konfigurowanych dla aplikacji mobilnej Warehouse Management. Gdy pracownicy magazynu otrzymują dobrze napisane instrukcje, mogą od razu zacząć korzystać z nowych przepływów bez konieczności wcześniejszego szkolenia. Ta funkcja zapewnia następujące korzyści:

- **Szybsze wdrażanie pracowników za pomocą prostych instrukcji wykonywania każdego kroku zadania.** Każdy krok przepływu zawiera instrukcje umożliwiające pracownikom pierwszej linii zrozumienie zadania.
- **Podawanie instrukcji zgodne z własnymi procesami.** Piszesz własne instrukcje, dostosowując je do swoich procesów biznesowych i magazynowych. Można na przykład dopasować terminologię do miejsca fizycznego i skrótów lokalnych.

## <a name="turn-on-the-warehouse-app-step-instructions-feature"></a>Włączanie funkcji instrukcji kroków aplikacji magazynu

Aby używać tej funkcji, należy ją włączyć w systemie. Od wersji 10.0.29 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Instrukcje kroku aplikacji magazynowej Warehouse* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="step-titles-and-step-instructions-in-the-app"></a>Tytuły kroków i instrukcje dotyczące kroków w aplikacji

Każdy krok przepływu zadań w aplikacji mobilnej Warehouse Management jest identyfikowany za pomocą identyfikatora kroku. Ponadto każdy krok ma tytuł, ikonę i instrukcję. (Aby uzyskać więcej informacji, zobacz temat [Przypisywanie ikon i tytułów kroków aplikacji mobilnej Warehouse Management](step-icons-titles.md)).

### <a name="step-titles"></a>Tytuły kroków

*Tytuł kroku* to krótki opis tego, co pracownik powinien zrobić podczas kroku. Jest on wyświetlany dużym tekstem u góry ekranu, jak pokazano na poniższej ilustracji.

![Przykładowy tytuł kroku w aplikacji mobilnej Warehouse Management](media/wma-step-title.png "Przykładowy tytuł kroku w aplikacji mobilnej Warehouse Management")

> [!TIP]
> Ze względu na duży rozmiar tekstu należy próbować zachować możliwie jak najkrótsze tytuły kroków. W przeciwnym razie tekst może zostać obcięty. Jednak w przypadku długich tytułów pracownicy nadal mogą nacisnąć i przytrzymać ten tytuł, aby otworzyć okno dialogowe z pełnym tekstem.

### <a name="step-instructions"></a>Instrukcje do kroku

*Instrukcja kroku* to dłuższy opis, który zawiera więcej informacji o tym, co pracownik powinien zrobić podczas kroku. Pojawia się on w wyskakującym oknie dialogowym, tak jak pokazano na poniższej ilustracji.

![Przykładowa instrukcja kroku w aplikacji mobilnej Warehouse Management](media/wma-step-instructions.png "Przykładowa instrukcja kroku w aplikacji mobilnej Warehouse Management")

Instrukcja kroku jest automatycznie wyświetlana po otwarciu kroku. Pracownicy mogą je odrzucić, dotykając dowolne miejsce poza wyskakującym oknem dialogowym. Ponadto to okno dialogowe zawiera pole wyboru **Nie pokazuj ponownie**, które pracownicy mogą zaznaczyć, aby instrukcji nie była wyświetlana przy następnym wykonywaniu tego samego zadania.

## <a name="load-the-default-setup"></a>Ładowanie ustawień domyślnych

Po pierwszym włączeniu funkcji *Instrukcje kroków aplikacji magazynu* system nie będzie zawierał żadnych dostosowanych tytułów ani instrukcji kroków. Dlatego najpierw należy załadować konfigurację domyślną. Konfiguracja domyślna zawiera teksty wszystkich dostępnych identyfikatorów kroku w każdym obsługiwanym języku. Procedura ładowania konfiguracji domyślnej jest następująca.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. W okienku akcji wybierz **Utwórz konfigurację domyślną**. Strona jest wypełniona standardowymi krokami.

## <a name="customize-step-titles-and-instructions"></a>Dostosowywanie tytułów i instrukcji kroków

Aby dostosować tytuł i/lub instrukcję kroku w dowolnej liczbie języków, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.

    Na stronie **Kroki urządzenia przenośnego** znajduje się lista czynności dostępnych w systemie. Każdy identyfikator kroku można udostępnić dowolnej liczbie opcji menu urządzenia przenośnego. Jeśli identyfikator kroku jest udostępniany wielu opcjom menu, dla wszystkich tych opcji menu jest wyświetlany ten sam tytuł i instrukcja. Można jednak utworzyć zastąpienia w celu dostosowania tytułu i instrukcji dla określonych opcji menu. (Aby uzyskać więcej informacji, zapoznaj się z następną sekcją).

    Siatka zawiera następujące kolumny:

    - **Nazwa opcji menu** — w wierszach, w których kolumna jest pusta, jest używany domyślny tytuł i instrukcja kroku obowiązujące wszystkie opcje menu urządzenia przenośnego, dla których nie zdefiniowano zastępowania. Wiersze, w których jako kolumna jest ustawiona nazwa opcji menu, mają zastąpienia stosowane tylko do określonej opcji menu.
    - **Identyfikator kroku** — unikatowy identyfikator kroku.
    - **Tytuł wprowadzania** — ten tytuł jest wyświetlany, gdy aplikacja żąda nowych informacji. Zwykle pola na stronie są puste (nie mają wstępnie ustawionych wartości).
    - **Tytuł potwierdzenia** — ten tytuł jest wyświetlany, gdy aplikacja żąda potwierdzenia wartości, która jest już przechowywana w systemie. Zazwyczaj pola na stronie mają wstępnie ustawione wartości.

1. Znajdź kombinację wartości **Identyfikator kroku** i **Nazwa opcji menu**, które chcesz edytować, i wybierz wartość w kolumnie **Identyfikator kroku**. Na otwartej stronie znajduje się lista wszystkich dostępnych tłumaczeń tytułu i instrukcji wybranego kroku.
1. Aby dostosować tekst w dowolnym języku, wykonaj jedną z poniższych czynności. Obie opcje umożliwiają edytowanie tekstów w istniejących językach. Jednak tylko pierwsza opcja umożliwia dodawanie tekstów w nowych językach, podczas gdy tylko druga opcja umożliwia przeglądanie i edytowanie tekstów wszystkich istniejących zastąpień wybranego języka.

    - Na pasku narzędzi wybierz opcję **Dodaj**, aby otworzyć okno dialogowe, w którym można dodawać lub edytować teksty w dowolnym obsługiwanym języku. W polu **Język odwołania** ustaw język, którego wartości chcesz wyświetlić. Wartości są wyświetlane w lewej kolumnie. W polu **Język pola tłumaczeń** ustaw język, który chcesz dodać lub dostosować. W prawej kolumnie zmodyfikuj wartości pól **Tytuł wprowadzania**, **Instrukcja wprowadzania**, **Tytuł potwierdzenia** i **Instrukcja potwierdzenia**, jeśli jest to wymagane. Następnie wybierz opcję **OK**.
    - W siatce znajdź i wybierz wiersz, w którym w polu **Język** jest ustawiony język, który chcesz edytować. Na pasku narzędzi wybierz polecenie **Wyświetl tłumaczenia tego kroku na &lt;język&gt;**, aby otworzyć okno dialogowe, w którym można edytować teksty wszystkich dostępnych zastąpień w wybranym języku. To okno dialogowe zawiera siatkę z wierszami zarówno tekstów standardowych (pole **Nazwa opcji menu** jest puste), jak i każdego dostępnego tekstu zastąpienia (gdzie w polu **Nazwa opcji menu** ustawiono nazwę opcji menu, której dotyczy zastąpienie). Zmodyfikuj wartości pól **Tytuł wprowadzania**, **Instrukcja wprowadzania**, **Tytuł potwierdzenia** i **Instrukcja potwierdzenia**, jeśli jest to wymagane. Następnie wybierz opcję **OK**.

1. Kontynuuj pracę, dopóki nie zdefiniujesz wszystkich wymaganych tytułów i instrukcji w każdym wymaganym języku.

## <a name="add-menu-specific-overrides"></a>Dodawanie zastąpień specyficznych dla menu

Jak wspomniano w poprzedniej sekcji, dla każdego identyfikatora kroku można utworzyć dowolną liczbę zastąpień specyficznych dla menu. Tej możliwości można używać do edytowania i zmieniania instrukcji, tak aby lepiej pasowała do lokalnego procesu biznesowego przypisanego do określonej opcji menu. Na przykład w przypadku kompletacji sprzedaży, jeśli firma zazwyczaj dostarcza pracownikom identyfikatory pracy na wydruku, można podać wskazówkę, aby pracownicy na początek skanowali identyfikator pracy.

Każde zastąpienie dotyczy określonej opcji menu urządzenia przenośnego i może zawierać dowolną liczbę tłumaczeń. Jeśli dla opcji menu nie istnieje żadna zastąpienie, są używane teksty standardowe opcji menu. Jeśli w danym języku nie zdefiniowano tłumaczenia zastępującego, będą używane teksty standardowe, nawet w przypadku opcji menu, w których zdefiniowano zastępowanie dla innych języków.

Aby utworzyć i skonfigurować zastąpienie, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. W siatce znajdź i wybierz wiersz, którego zastąpienie ma być utworzone.
1. W okienku akcji wybierz pozycję **Dodaj konfigurację kroku**.
1. W oknie dialogowym **Dodawanie konfiguracji kroku** ustaw w polu **Opcja menu** nazwę opcji menu urządzenia przenośnego, do której ma zastosowanie zastąpienie. Następnie wybierz opcję **OK**.
1. Na stronie zostaną wyświetlone wszystkie teksty dostępne dla nowego zastąpienia. Początkowo jest tworzony tylko jeden język. Do czasu dodania tych języków w tym miejscu wszystkie inne języki będą nadal używać tych tekstów standardowych. Zmodyfikuj teksty i dodaj nowe języki zgodnie z wymaganiami w sposób opisany w poprzedniej sekcji.

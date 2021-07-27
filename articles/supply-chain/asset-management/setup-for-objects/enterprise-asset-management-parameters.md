---
title: Parametry zarządzania składnikami majątku
description: W module Zarządzanie składnikami majątku należy skonfigurować ogólne parametry odnoszące się do składników majątku, zleceń pracy i planowania zlecenia pracy.
author: johanhoffmann
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6affcc20c2c2e2b8fa9e38cb523e172bb2a79f22
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349825"
---
# <a name="asset-management-parameters"></a>Parametry zarządzania składnikami majątku

[!include [banner](../../includes/banner.md)]

W module Zarządzanie składnikami majątku należy skonfigurować ogólne parametry odnoszące się do składników majątku, zleceń pracy i planowania zlecenia pracy. W tym temacie wyjaśniono sposób ich konfigurowania. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Parametry zarządzania składnikami majątku**, aby otworzyć stronę.

> [!NOTE]
> Aby skonfigurować system obejmujący dane demonstracyjne dotyczące testowania funkcji Zarządzania składnikami majątku, zapoznaj się z tematem [Wdrażanie środowiska demonstracyjnego](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).

## <a name="the-assets-tab"></a>Karta Składniki majątku

Karta **Składniki majątku** zawiera następujące ustawienia:

- **Domyślną lokalizacją czynności konserwacyjnych** jest standardowa lokalizacja czynności konserwacyjnych, która jest automatycznie wybierana w składnikach majątku podczas tworzenia nowych składników majątku.  
- W polu **Standardowy kalendarz** wybierz kalendarz, który ma być używany do obliczania wskaźników KPI składnika majątku, jeśli składnik majątku nie jest zaznaczony.  
- W polu **Widok** wybierz widok standardowy, który jest wyświetlany po otwarciu **Widok składnika majątku** (**Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Widok składników majątku**).
- **Domyślny typ żądania** to standardowy typ żądania konserwacji, który jest wybierany automatycznie podczas tworzenia nowego żądania.  
- Prognozy dotyczące typów zadań są przechowywane w projekcie wybranym w polu **Projekt prognozy**. Dla każdego typu zadania nowe działanie jest tworzone automatycznie w projekcie prognozy. Prognozy dotyczące typu zadania są następnie zapisywane w projekcie prognozy.  
- W polu **Model** wybierz model prognozy używany dla typu zadania i prognoz zleceń pracy.

## <a name="the-work-orders-tab"></a>Karta Zlecenia pracy

Karta **Zlecenia pracy** zawiera następujące ustawienia:

- **Domyślny typ zlecenia** definiuje ustawienia standardowe podczas tworzenia zlecenia pracy.  
- **Typ zlecenia prewencyjnego** definiuje typ zlecenia pracy używany podczas tworzenia zleceń pracy z planów konserwacji. Jeśli to pole pozostanie puste, używany jest typ zlecenia pracy określony w polu **Domyślny typ zlecenia pracy**.  
- W polu **Maska powiązanego zlecenia pracy** definiuje się maksymalną liczbę zleceń pracy, które mogą być związane ze zleceniem pracy. Na przykład, ## pozwala na posiadanie do powiązanych 99 zleceń pracy. Jeśli zdefiniujesz maskę zgodnie z opisem w tym miejscu, powiązane zlecenia pracy będą numerowane [identyfikator zlecenia pracy, z którym jest powiązane zlecenie pracy]-01,-02,-03 itd. Jeśli nie zdefiniujesz maski w tym polu, powiązane zlecenie pracy otrzyma następny sekwencyjny identyfikator zlecenia pracy.  
- Wybierz **Tak** na przełączniku **Błędy kopiowania**, jeśli chcesz automatycznie kopiować błędy zarejestrowane w zleceniach pracy do powiązanych żądań konserwacji. 
- W polu **Poziom** można zdefiniować poziom lokalizacji czynności konserwacyjnych, który jest automatycznie wstawiany w zleceniu pracy, jeśli wszystkie powiązane zadania zlecenia pracy odnoszą się do tej samej lokalizacji czynności konserwacyjnych. Jeśli zadania zlecenia pracy nie odnoszą się do tej samej lokalizacji czynności konserwacyjnych na zdefiniowanym poziomie, pole **Lokalizacja czynności konserwacyjnych** jest pusta na zleceniu pracy. Na przykład, jeśli wstawisz cyfrę „1” w tym polu, to jest to najwyższy poziom w strukturze lokalizacji czynności konserwacyjnych. Jeśli w tym polu zostanie wstawiona cyfra „0”, nie zdefiniowano określonego poziomu lokalizacji czynności konserwacyjnych, tylko że wszystkie zadania zlecenia pracy w zleceniu pracy muszą być powiązane z tą samą lokalizacją czynności konserwacyjnych dla tej lokalizacji czynności konserwacyjnych, która ma zostać dodana do zlecenia pracy.  
- Arkusze używane podczas księgowania zużycia na zleceniu pracy można wybrać na skróconej karcie **Ogólne** w polach **Godzina**, **Zapas** i **Wydatek**.  
- W polu **Źródło języka produktu** wybierz język, który ma być używany dla nazw produktów w raportach modułu Zarządzanie składnikami majątku. Można wybrać język skonfigurowany dla konta firmowego lub język skonfigurowany dla aktualnie zalogowanego użytkownika.  
- Wybierz wartość **Tak** na **Aktualizacje w czasie rzeczywistym**, jeśli chcesz automatycznie aktualizować zmiany domyślnych wartości typu zadania, planów konserwacji i seriach czynności konserwacyjnych.
  - W przypadku wybrania opcji **Nie** zmiany wartości domyślnych typu zadania, planów konserwacji i serii czynności konserwacyjnych nie będą aktualizowane automatycznie w module Zarządzanie składnikami majątku.
  - Wybierz opcję **Nie**, jeśli masz zsynchronizowaną dużą ilość danych, na przykład wiele składników majątku lub lokalizacji czynności konserwacyjnych skonfigurowanych na planach konserwacji lub seriach czynności konserwacyjnych, lub dużą liczbę planów konserwacyjnych lub serii czynności konserwacyjnych.  
  - Jeśli zostaną wprowadzone zmiany w ustawieniach domyślnych typu zadania lub w planach konserwacji lub serii czynności konserwacyjnych, a wybrano opcję **Nie** w odniesieniu do aktualizacji w czasie rzeczywisty, ostrzeżenie nie może być wyświetlane, jeśli zmiany wpływają na:
    - Lokalizacje czynności konserwacyjnych ustawione w planach konserwacji lub serii czynności konserwacyjnych  
    - Obiekty skonfigurowane w planach konserwacji lub serii czynności konserwacyjnych  
    - Konfigurację planów konserwacji  
    - Konfigurację serii czynności konserwacyjnych  
- Na skróconej karcie **Kategoria** znajdują się domyślne kategorie odnoszące się do zużycia w zleceniach pracy.  

## <a name="the-work-order-scheduling-tab"></a>Karta Planowanie zlecenia pracy

Karta **Planowanie zlecenia pracy** zawiera następujące ustawienia na skróconej karcie **Ogólne**:

- **Horyzont czasowy harmonogramu** określa okres w dniach, obliczony od oczekiwanej daty rozpoczęcia zlecenia pracy, podczas którego są planowane zadania dotyczące zlecenia pracy.  
- **Plan główny** odnosi się do zasobów w module **Administrowanie organizacją**. Jeśli w tym polu zostanie wybrany plan główny, można wyświetlić rezerwacje zdolności produkcyjnych związane ze zleceniami pracy w **Rezerwacji zdolności produkcyjnych** (**Administrowanie organizacją** > **Zasoby** > **Zasoby** > wybierz zasób > karta **Zasób** > przycisk **Rezerwacja zdolności produkcyjnych**). Jeśli zostawisz to pole puste, będzie można wyświetlić obciążenie zdolności produkcyjnych powiązane ze zleceniami pracy w **Obciążeniu zdolności produkcyjnych** (**Administrowanie organizacją** \> **Zasoby** \> **Zasoby** wybierz zasób \> karta \> **Zasób** \> przycisk **Rezerwacja zdolności produkcyjnych**).  

>[!NOTE]
>Wybór dotyczy używania planu głównego w module **Zarządzanie składnikami majątku**, a pokrewnym formularzem używanym do przeglądu rezerwacji zdolności produkcyjnych lub obciążenia zdolności produkcyjnych jest standardowa konfiguracja. Zależnie od ustawień w polu **Plan główny** można uzyskać dostęp do informacji o zdolnościach produkcyjnych w obszarach **Rezerwacjach zdolności produkcyjnych** lub **Obciążenie wydajności** w module **Administrowanie organizacją**. Nie można utworzyć konfiguracji, w której rezerwacje zdolności produkcyjnych są wyświetlane w obu widokach.  

Pola opisane poniżej na liście poniżej odnoszą się do obliczonych wyników oceny, które są używane do obliczania priorytetu zlecenia pracy podczas planowania zleceń pracy.

- **Priorytet** — wynik oceny obliczony razem z wynikiem oceny w polach **Krytyczność** i **Data początkowa**. Liczba w tym polu jest dzielony przez numer z pola **Priorytet** w zleceniu pracy. na przykład, jeśli w tym polu zostanie wstawiona wartość „5,00”, a zlecenie produkcyjne ma priorytet „20”, wynik oceny priorytetu wynosi 0,25.  
- **Krytyczność** — wynik oceny obliczony razem z wynikiem oceny w polach **Priorytet** i **Data początkowa**. Numer w tym polu jest mnożony przez liczbę z pola **Krytyczność** w zleceniu pracy. Na przykład, jeśli w tym polu zostanie wstawiona wartość „10,00”, a zlecenie produkcyjne ma krytyczność „5”, wynik oceny krytyczności wynosi 50.  
- **Data początkowa** — wynik oceny obliczony razem z wynikiem oceny w polach **Priorytet** i **Krytyczność**. To pole wskazuje dzienny wynik jako wartość ujemną i jest porównywane z polem **Oczekiwana data rozpoczęcia** w zleceniu pracy. Na przykład, jeśli w tym polu zostanie wstawiona wartość „10,00”, a oczekiwana data rozpoczęcia zlecenia produkcyjnego wynosi trzy dni od chwili obecnej, wynik oceny wynosi minus 30,00. Dodanie wyników 0,25 i 50 z przykładów w polach **Priorytet** i **Krytyczność** opisanych powyżej stanowi łączną sumę plus 20,25. Ta liczba jest porównywana z wszystkimi wynikami oceny zlecenia pracy w trakcie planowania zleceń pracy, a najwyższe wyniki oceny są następnie planowane jako pierwsze.  
- **Odpowiedzialny pracownik** — wynik oceny obliczony razem z wartościami oceny **Grupa odpowiedzialnych pracowników**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. Jeśli wartość „50,00” jest wstawiona w tym polu, a odpowiedzialny pracownik został wybrany w zleceniu pracy, pracownik otrzyma 50 punktów w ogólnej kalkulacji pracownika w trakcie planowania zlecenia.  
- **Grupa odpowiedzialnych pracowników** — wynik oceny obliczony razem z wartościami oceny **Odpowiedzialny pracownik**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. Jeśli wartość „50,00” jest wstawiona w tym polu, a odpowiedzialny pracownik został wybrany w zleceniu pracy, pracownik otrzyma 50 punktów w ogólnej kalkulacji pracownika w trakcie planowania zlecenia.  
- **Ogranicz do osoby odpowiedzialnej** - ogranicza liczbę pracowników dostępnych dla planowania zlecenia pracy. Wybierz **Nie**, jeśli chcesz obliczyć punktację dla wszystkich pracowników, niezależnie od tego, czy są oni skonfigurowani jako pracownicy odpowiedzialni, czy jako członkowie grupy pracowników odpowiedzialnych. Wybierz **Tak**, jeśli chcesz obliczyć wynik dla pracowników, którzy są skonfigurowani jako pracownicy odpowiedzialni na zleceniu pracy i/lub znajdują się w grupie pracowników odpowiedzialnych wybranych w zleceniu pracy.  
- **Preferowany pracownik** — wynik oceny obliczony razem z wartościami oceny **Odpowiedzialny pracownik**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. Cztery wyniki ocen są obliczane i dodawane do siebie w celu określenia punktacji służącej do wybrania pracownika, któremu należy przypisać zlecenie pracy w trakcie planowania zleceń pracy. Jeśli wartość „10,00” jest wstawiona w tym polu, a pracownik został wybrany jako preferowany w zleceniu pracy, pracownik otrzyma 10 punktów w ogólnej kalkulacji pracownika w trakcie planowania zlecenia.  
- **Grupa preferowanych pracowników** — wynik oceny obliczony razem z wartościami oceny **Odpowiedzialny pracownik**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. Jeśli wartość „10,00” jest wstawiona w tym polu, a pracownik został przypisany do grupy preferowanych pracowników wybranych w zleceniu pracy, pracownik otrzyma 10 punktów w ogólnej kalkulacji pracownika w trakcie planowania zlecenia.  
- **Ogranicz do osoby preferowanej** - ogranicza liczbę pracowników dostępnych dla planowania zlecenia pracy. Wybierz **Nie**, jeśli chcesz obliczyć punktację dla wszystkich pracowników, niezależnie od tego, czy są oni skonfigurowani jako pracownicy preferowani, czy jako członkowie grupy pracowników preferowanych. Wybierz **Tak**, jeśli chcesz obliczyć punktację tylko dla pracowników, którzy są skonfigurowani jako pracownicy preferowani i/lub jako członkowie grupy pracowników preferowanych.  
- **Lokalizacja** — wynik oceny obliczony razem z wartościami oceny **Odpowiedzialny pracownik**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. Jeśli w tym polu zostanie wstawiona wartość „3 000,00”, pracownik otrzymuje 3 000 punków w obliczeniach, jeśli pracownik jest zlokalizowany w tej samej fabryce lub placówce, co składnik majątku, w którym ma być zaplanowane zadanie.  
  - Jeśli firma korzysta z lokalizacji czynności konserwacyjnych, pracownicy otrzymują pełną punktację, jeśli znajdują się w lokalizacji czynności konserwacyjnych związanej z składnikiem majątku. Jeśli funkcjonalna czynności konserwacyjnych składnika majątku ma nadrzędny składnik majątku, pracownicy w tej lokalizacji czynności konserwacyjnych otrzymują 1/2 wyniku. Jeśli ta lokalizacja ma również element nadrzędny, pracownicy w tej lokalizacji otrzymują 1/3 wyniku. Jeśli ta lokalizacja ma również element nadrzędny, pracownicy w tej lokalizacji otrzymują 1/4 wyniku itd.  
  - Jeśli firma korzysta z lokalizacji składnika majątku, której nie zalecamy, lokalizacja, obszar i strefa są używane do obliczania wyników lokalizacji. Pracownicy otrzymują pełny wynik, jeśli znajdują się w lokalizacji i obszarze oraz strefie związanych ze składnikiem majątku. Jeśli lokalizacja pracownika jest zgodna tylko z lokalizacją i obszarem, wynik oceny dla pracownika wynosi 2/3 pełnego wyniku. Jeśli lokalizacja pracownika jest zgodna tylko z lokalizacją, wynik oceny dla pracownika wynosi 1/3 pełnego wyniku.  
- **Ogranicz do lokalizacji** - ogranicza liczbę pracowników dostępnych dla planowania zlecenia pracy. Wybierz **Nie**, jeśli chcesz obliczyć wynik dla wszystkich pracowników we wszystkich lokalizacjach czynności konserwacyjnych. Wybierz **Tak**, jeśli chcesz obliczyć wynik tylko dla pracowników, którzy są powiązani z lokalizacją czynności konserwacyjnych zlecenia pracy.

>[!NOTE]
>Trzy pola „Ogranicz do...” zwiększają szybkość planowania zleceń pracy poprzez ograniczenie liczby wyników obliczanych dla pracowników.

**Data rozpoczęcia pracownika** — wynik oceny obliczony razem z wartościami oceny **Odpowiedzialny pracownik**, **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa**. To pole wskazuje dzienny wynik jako wartość ujemną i jest porównywane z polem **Oczekiwana data rozpoczęcia** w zleceniu pracy. Jeśli w tym polu zostanie wstawiona wartość „10,00”, a oczekiwana data rozpoczęcia zlecenia produkcyjnego jest jutro, wynik oceny wynosi minus 10,00.

  - Przy założeniu, że żaden odpowiedzialny pracownik ani grupa odpowiedzialnych pracowników nie zostały wybrane w zleceniu pracy do zaplanowania — dodajesz i odejmujesz przykładowe wartości wyniku oceny w polach **Preferowany pracownik**, **Grupa preferowanych pracowników**, **Lokalizacja składnika majątku** oraz **Data początkowa** powyżej i otrzymujesz sumę 3 010,00. Oznacza to wysoki wynik dla pracownika, który jest już wybrany jako preferowany pracownik, a także uwzględniony w grupie preferowanych pracowników w zleceniu pracy, i pracownik znajduje się również w tym samym obiekcie co składnik majątku, dla którego musi zostać zaplanowane zadanie. Oznacza to, że istnieje duża szansa, że pracownik, o którym mowa, zostanie wybrany do ukończenia zadania podczas planowania zlecenia pracy.  
  - Jeśli wartość „0,00” jest wstawiana w jednym z ośmiu pól powyżej, ten wynik oceny nie będzie używany podczas planowania zlecenia pracy.  

## <a name="the-document-types-tab"></a>Karta Typy dokumentów

Wybierz typy dokumentów, które powinny być dostępne do drukowania załączników związanych z raportem zlecenia pracy. W tym celu wybierz typ dokumentu w sekcji **Dostępne** i wybierz ![strzałkę do przodu.](media/15-setup-for-objects.png). Jeśli chcesz usunąć wybrany typ dokumentu, wybierz typ dokumentu w sekcji **Wybrane**, a następnie wybierz ![strzałkę wstecz](media/16-setup-for-objects.png).

## <a name="the-number-sequences-tab"></a>Karta Sekwencje numerów

Wybierz żądane sekwencje numerów w tej sekcji. Istnieją dwie sekwencje numerów dla składników majątku: jedna dla składników majątku utworzonych ręcznie, a druga dla składników majątku utworzonych za pośrednictwem oczekujących składników majątku.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
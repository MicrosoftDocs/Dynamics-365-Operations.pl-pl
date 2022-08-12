---
title: Prognozowanie przepływów pieniężnych
description: Ten artykuł zawiera omówienie procesu prognozowania przepływów pieniężnych. Wyjaśniono również, jak prognozowanie przepływów pieniężnych jest zintegrowane z innych modułami w systemie.
author: angelad116
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: d76e47fc1456dfab7606f337f070a149b0c8e586
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151949"
---
# <a name="cash-flow-forecasting"></a>Prognozowanie przepływów pieniężnych

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Narzędzia prognozowania przepływów pieniężnych mogą służyć do analizy nadchodzących przepływów pieniężnych i zapotrzebowania na waluty, co pozwoli szacować przyszłe potrzeby firmy w zakresie gotówki. Aby uzyskać prognozę przepływów pieniężnych, należy wykonać następujące zadania:

- Zidentyfikowanie wszystkich kont płynności i sporządzenie ich listy. Konta płynności to firmowe konta kasowe i aktywów finansowych.
- Skonfigurowanie zachowania prognoz dla transakcji, które mają wpływ na konta płynności firmy.

Po wykonaniu tych zadań można obliczać i analizować prognozy przepływów pieniężnych i nadchodzących zapotrzebowań na waluty.

## <a name="cash-flow-forecasting-integration"></a>Integracja prognozowania przepływów pieniężnych

Funkcjonalność prognozowania środków pieniężnych można zintegrować z modułami Księga główna, Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Budżetowanie i Zarządzanie zapasami. Proces prognozowania używa informacji o transakcjach wprowadzonych w systemie, a proces obliczania prognozuje oczekiwany skutek gotówkowy każdej transakcji. Następujące typy transakcji są uwzględniane podczas obliczania przepływ pieniężnych:

- **Zamówienia sprzedaży** — zamówienia sprzedaży, które nie zostały jeszcze zafakturowane i które skutkują fizyczną lub finansową sprzedażą.
- **Faktury niezależne** — faktury niezależne, które nie zostały jeszcze zaksięgowane i których wynikiem jest sprzedaż finansowa. 
- **Zamówienia zakupu** — zamówienia zakupu, które nie zostały jeszcze zafakturowane i które skutkują fizycznym lub finansowym zakupem.
- **Rozrachunki z odbiorcami** — otwarte transakcje z odbiorcami (faktury nie są jeszcze zapłacone).
- **Rozrachunki z dostawcami** — otwarte transakcje z dostawcami (faktury nie są jeszcze zapłacone).
- **Transakcje księgi** — transakcje, w których określono, że w przyszłości nastąpi zaksięgowanie.
- **Wpisy do rejestru budżetu** — wpisy do rejestru budżetu, które wybrano dla prognoz przepływów pieniężnych.
- **Prognozy popytu** — wiersze modelu prognozy zapasów, które wybrano dla prognoz przepływów pieniężnych.
- **Prognozy dostaw** — wiersze modelu prognozy zapasów, które wybrano dla prognoz przepływów pieniężnych.
- **Zewnętrzne źródło danych** — dane zewnętrzne wprowadzane lub importowane do prognoz przepływów pieniężnych za pomocą szablonów arkuszy kalkulacyjnych.
- **Prognozy projektów** — prognozy zarządzania projektami i ich księgowania za pomocą modelu prognozy.
- **Przepływy pieniężne — płatności do urzędu skarbowego** — przewidywane kwoty płatności do urzędu skarbowego oraz terminy, których wynikiem są płatności finansowe. Włącz funkcję Przepływy pieniężne — płatności do urzędu skarbowego.

## <a name="configuration"></a>Konfiguracja

Proces prognozowania przepływów pieniężnych można skonfigurować za pomocą strony **Ustawienia prognozy przepływów pieniężnych**. Na tej stronie określasz konta płynności, które mają być śledzone, oraz domyślne zachowanie prognozowania dla każdego obszaru.

### <a name="general-ledger"></a>Księga główna

Najpierw należy określić konta płynności, które mają być śledzone w całym procesie prognozowania przepływów pieniężnych. Zazwyczaj te konta płynności są kontami głównymi skojarzonymi z kontami bankowych, na których będzie wpłacana i wypłacana gotówka. Na stronie **Ustawienia prognozy przepływów pieniężnych** na karcie **Księga główna** wybierz konta główne, które mają być uwzględniane w prognozowaniu. Jeśli konto bankowe skojarzono z kontem głównym na stronie **Konto bankowe**, jest ono wyświetlane w polu **Konto bankowe**.

Istnieje możliwość skonfigurowania zależnej prognozy przepływów pieniężnych dla konta głównego zawierającego transakcje, które są bezpośrednio związane z transakcjami na innym koncie głównym. Każdy wiersz dodany w sekcji **Konta zależne** tworzy kwotę prognozy przepływów pieniężnych na zależnym koncie głównym. Ta kwota jest procentem kwot przepływów pieniężnych do wybranego podstawowego konta głównego.

Najpierw w polu **Konto główne** ustaw podstawowe konto główne, na którym oczekuje się, że początkowo będą dokonywane transakcje. W polu **Zależne konta główne** ustaw konto, na które będą miały wpływ początkowe transakcje dokonywane na podstawowym koncie głównym. Ustaw odpowiednie wartości w pozostałych polach w wierszu. Można zmienić wartość w polu **Procent**, aby odzwierciedlała ona wpływ podstawowego konta głównego na zależne konto główne. Przy prognozowaniu sprzedaży lub zakupów w polu **Warunki płatności** należy wybrać wartość typową dla większości odbiorców lub nabywców. W polu **Typ księgowania** ustaw oczekiwany typ księgowania powiązany z prognozą przepływów pieniężnych.

### <a name="accounts-payable"></a>Rozrachunki z dostawcami

Prognozy dla zakupów można obliczać za pomocą opcji konfiguracji na karcie **Rozrachunki z dostawcami** na stronie **Ustawienia prognozy przepływów pieniężnych**. Aby można było skonfigurować prognozowania przepływów pieniężnych dla rozrachunków z dostawcami, należy skonfigurować warunki płatności, grupy dostawców i profile księgowania dostawców.

W sekcji **Ustawienia domyślne prognoz zakupów** można wybrać domyślne zachowania zakupowe dla prognozowania przepływów pieniężnych. Trzy pola określają czas skutku gotówkowego: **Czas między datą dostawy a datą faktury**, **Warunki płatności** i **Czas między datą wymagalności faktury a datą płatności**. Prognoza użyje domyślnego ustawienia z pola **Warunki płatności** tylko wtedy, gdy wartość nie jest określona w transakcji. Warunek płatności służy do opisywania najbardziej typowej liczby dni dla każdej części procesu.

Pole **Konto płynności dla płatności** określa konto płynności, która jest najczęściej używane dla płatności. W polu **Procent kwoty do przydzielenia do prognozy przepływów pieniężnych** określ, czy podczas prognozowania ma być używany procent kwot. Pozostaw to pole puste, jeśli w prognozowaniu mają być używane pełne kwoty transakcji.

Możesz zastąpić domyślną wartość w polu **Czas między datą wymagalności faktury a datą płatności** dla określonych grup dostawców. Prognoza będzie używać wartości domyślnej z sekcji **Ustawienia domyślne prognoz zakupów**, chyba że zostanie określona inna wartość dla grupy dostawców powiązanej z dostawcą w transakcji. Aby zastąpić wartość domyślną, zaznacz grupę dostawców, a następnie ustaw nową wartość w polu **Czas zakupu**.

Możesz zastąpić domyślną wartość w polu **Konto płynności** dla konkretnych profili księgowania dostawców. Prognoza będzie używać wartości domyślnej z sekcji **Ustawienia domyślne prognoz zakupów**, chyba że zostanie określone inne konto płynności dla profilu księgowania powiązanego z dostawcą w transakcji. Aby zastąpić wartość domyślną, zaznacz profil księgowania, a następnie określ konto płynności, na które mają być wywierane skutki.

### <a name="accounts-receivable"></a>Rozrachunki z odbiorcami

Prognozy dla sprzedaży można obliczać za pomocą opcji konfiguracji na karcie **Rozrachunki z odbiorcami** na stronie **Ustawienia prognozy przepływów pieniężnych**. Aby można było skonfigurować prognozowania przepływów pieniężnych dla rozrachunków z odbiorcami, należy skonfigurować warunki płatności, grupy odbiorców i profile księgowania odbiorców.

W sekcji **Ustawienia domyślne prognoz sprzedaży** można wybrać domyślne zachowania sprzedażowe dla prognozowania przepływów pieniężnych. Trzy pola określają czas skutku gotówkowego: **Czas między datą wysyłki a datą faktury**, **Warunki płatności** i **Czas między datą wymagalności faktury a datą płatności**. Prognoza użyje domyślnego ustawienia z pola **Warunki płatności** tylko wtedy, gdy wartość nie jest określona w transakcji. Warunek płatności służy do opisywania najbardziej typowej liczby dni dla każdej części procesu. 

Pole **Konto płynności dla płatności** określa konto płynności, która jest najczęściej używane dla płatności. W polu **Procent kwoty do przydzielenia do prognozy przepływów pieniężnych** określ, czy podczas prognozowania ma być używany procent kwot. Pozostaw to pole puste, jeśli w prognozowaniu mają być używane pełne kwoty transakcji.

Możesz zastąpić domyślną wartość w polu **Czas między datą wymagalności faktury a datą płatności** dla określonych grup odbiorców. Prognoza będzie używać wartości domyślnej z sekcji **Ustawienia domyślne prognoz sprzedaży**, chyba że zostanie określona inna wartość dla grupy odbiorców powiązanej z odbiorcą w transakcji. Aby zastąpić wartość domyślną, zaznacz grupę odbiorców, a następnie ustaw nową wartość w polu **Czas sprzedaży**.

Możesz zastąpić domyślną wartość w polu **Konto płynności** dla konkretnych profili księgowania odbiorców. Prognoza będzie używać wartości domyślnej z sekcji **Ustawienia domyślne prognoz sprzedaży**, chyba że zostanie określone inne konto płynności dla profilu księgowania powiązanego z odbiorcą w transakcji. Aby zastąpić wartość domyślną, zaznacz profil księgowania, a następnie ustaw konto płynności, na które mają być wywierane skutki.

### <a name="budgeting"></a>Budżetowanie

Budżety tworzone na podstawie modeli budżetu można uwzględniać w prognozach przepływów pieniężnych. Na stronie **Ustawienia prognozy przepływów pieniężnych** na karcie **Budżetowanie** zaznacz modele budżetu do uwzględnienia w prognozie. Domyślnie nowe wpisy do rejestru budżetu są uwzględniane w prognozach po włączeniu opcji wykorzystywania modelu budżetu w prognozowaniu przepływów pieniężnych.

Wpisy do rejestru budżetowego mogą być indywidualnie uwzględniane w prognozie przepływów pieniężnych poprzez personalizację. Podczas dodawania kolumny „Uwzględnij w prognozach przepływów pieniężnych” na stronie **wpisu do rejestru budżetu** system zastąpi ustawienia na stronie **ustawień prognozy przepływów pieniężnych**, aby uwzględnić w prognozie pojedynczy wpis do rejestru budżetu.


### <a name="inventory-management"></a>Zarządzanie zapasami

W prognozach przepływów pieniężnych można uwzględniać prognozy dostaw zapasów i popytu na zapasy. Na stronie **Ustawienia prognozy przepływów pieniężnych** na karcie **Zarządzanie zapasami** zaznacz modelu prognozy do uwzględnienia w prognozie przepływów pieniężnych. Uwzględnianie w prognozowaniu przepływów pieniężnych można zastępować na poziomie poszczególnych wierszy prognoz dostaw i popytu.

### <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Konfigurowanie wymiarów dla prognozowania przepływów pieniężnych
Nowa karta na stronie  **Ustawienia prognozowania przepływów pieniężnych**  umożliwia kontrolowanie wymiarów finansowych, które będą używane w celu filtrowania w obszarze roboczym  **Prognozowanie przepływów pieniężnych** . Ta karta będzie wyświetlana tylko wtedy, gdy będzie włączona funkcja Prognozy przepływów pieniężnych.

Na karcie **Wymiary** wybierz z listy wymiary, które mają być użyte do filtrowania, a następnie za pomocą klawiszy strzałek przenieś je do prawej kolumny. Do filtrowania danych prognozy przepływów pieniężnych można wybrać tylko dwa wymiary. 

### <a name="setting-up-external-source"></a>Ustawianie źródła zewnętrznego
Po skonfigurowaniu aplikacji Finance Insights do prognoz przepływów pieniężnych można wprowadzać lub importować dane zewnętrzne. Przed wprowadzeniu lub zaimportowaniu danych zewnętrznych należy skonfigurować źródła zewnętrzne. Na karcie **Źródło zewnętrzne** skonfiguruj kategorie zewnętrznych przepływów pieniężnych. Może to być kategoria **Wychodząca** lub **Przychodząca**. Jako typ księgowania należy wybrać **płynność**. W siatce **Ustawienia firmy wybierz firmy** i odpowiednie konta główne, do których mają zastosowanie kategorie zewnętrznych przepływów pieniężnych.

Aby uzyskać więcej informacji, zobacz [Dane zewnętrzne w prognozach przepływów pieniężnych](../../finance/finance-insights/external-data-in-cash-flow.md). 

### <a name="project-management-and-accounting"></a>Zarządzanie projektami i ich księgowanie

W wersji 10.0.17 nowa funkcja umożliwia integrację z funkcjami zarządzania projektami i ich księgowania oraz prognozowania przepływów pieniężnych. W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Prognoza dla projektu przepływów pieniężnych**, aby uwzględnić prognozowane koszty i przychody w prognozie przepływów pieniężnych. Na karcie **Zarządzanie projektami i ich księgowanie** na stronie **Ustawienia prognozy przepływów pieniężnych** wybierz typy projektów i typy transakcji, które powinny być uwzględnione w prognozie przepływów pieniężnych. Następnie wybierz model prognozy projektu. Podmodel typu redukcji działa najlepiej. Konta płynności wprowadzone w ustawieniach rozrachunków z odbiorcami są używane jako domyślne konta płynności. Dlatego nie trzeba wprowadzać domyślnych kont płynności podczas ustawienia prognozy przepływów pieniężnych. Można również użyć modelu budżetu, ale tylko jeden typ można wybrać na stronie **Ustawień prognozy przepływów pieniężnych** dla zarządzania projektami i ich księgowania. Model prognozy oferuje najbardziej elastyczny sposób zarządzania projektami i ich księgowania lub działania w ramach Project Operations.

Po włączeniu funkcji prognozy przepływów pieniężnych można wyświetlać prognozę przepływów pieniężnych dla każdego projektu na stronie **Wszystkie projekty**. W okienku akcji na karcie **Plan** kliknij w grupie **Prognoza** wybierz opcję **Prognoza przepływów pieniężnych**. W obszarach roboczych **Przegląd gotówki** (zobacz sekcję [Raportowanie](#reporting) w dalszej części tego artykułu) typ transakcji prognozy projektu pokazuje przychody (przychód prognozy projektu) i przychody (koszty prognoz projektu). Kwoty można uwzględniać tylko wtedy, gdy pole **Etap projektu** w obszarze roboczym **Przegląd gotówki** ma wartość **W trakcie**.

Transakcje projektu są nadal uwzględniane w prognozie przepływów pieniężnych na kilka sposobów, niezależnie od tego, czy funkcja **Prognozy przepływów pieniężnych** jest włączona. Zaksięgowane faktury projektu są uwzględniane w prognozie jako część otwartych transakcji odbiorcy. Zamówienia sprzedaży i zamówienia zakupu inicjowane przez projekt są uwzględniane w prognozie jako otwarte zamówienia po ich wprowadzeniu w systemie. Można także przenieść prognozy projektu do modelu budżetu księgi. Następnie ten model budżetu księgi zostanie uwzględniony w prognozie przepływów pieniężnych jako część wpisów do rejestru budżetu. Jeśli funkcja **Prognozy projektu przepływów pieniężnych** jest włączona, nie należy przenosić prognoz projektu do modelu budżetu księgi, ponieważ ta akcja spowoduje zliczanie prognoz projektów dwa razy.

### <a name="sales-tax-authority-payments"></a>Płatności do urzędu skarbowego 

Funkcja Przepływy pieniężne — płatności do urzędu skarbowego przewiduje wpływ przepływów pieniężnych na płatności podatków. Ta funkcja używa niezapłaconych transakcji podatku, okresów rozliczania podatku oraz terminu płatności podatku w celu przewidywania daty i kwoty płatności związanych z przepływami pieniężnymi. 

### <a name="calculation"></a>Obliczanie

Aby można było wyświetlać analizy prognostyczne przepływów pieniężnych, należy uruchomić proces obliczania przepływów pieniężnych. Proces obliczania będzie prognozował przyszłe skutki gotówkowe wprowadzanych transakcji.

Obliczanie prognoz przepływów pieniężnych odbywa się na stronie **Oblicz prognozy przepływów pieniężnych**. Można obliczyć pełną prognozę przepływów pieniężnych lub przyrostową prognozę przepływów pieniężnych. 

- Aby wyczyścić wszystkie transakcje prognoz przepływów pieniężnych i wykonać ponowne obliczanie, w polu **Metoda obliczania prognoz przepływów pieniężnych** ustaw wartość **Suma**. Zalecamy stosowanie tej metody, jeśli prognozy przepływów pieniężnych nie były aktualizowane przez długi czas. 
- Aby zaktualizować istniejące dane przepływów pieniężnych wyłącznie dla nowych transakcji, w polu **Metoda obliczania prognoz przepływów pieniężnych** ustaw wartość **Nowy**. Na stronie będzie wyświetlana data ostatniej sesji obliczania przepływów pieniężnych.

Do prognozowania przepływów pieniężnych można także używać przetwarzania wsadowego. W celu zapewnienia, że analizy prognostyczne są regularnie aktualizowane, skonfiguruj cykliczny proces wsadowy obliczania prognoz przepływów pieniężnych.

W wersji 10.0.13 zostało wydane ulepszenie procesu obliczania, które korzysta z struktury automatyzacji procesu w celu zaplanowania zadania obliczania przepływu pieniężnego. Jest to możliwe dzięki użyciu funkcji **Automatyzacja prognoz przepływów pieniężnych** w obszarze roboczym **Zarządzanie funkcjami**. Po włączeniu tego pola należy wybrać łącze **Automatyzacja prognoz przepływów pieniężnych**, aby wyświetlić stronę nowa automatyzacja, na której można zaplanować proces obliczania przepływu pieniężnego. Aby utworzyć nowy harmonogram prognozy przepływów pieniężnych, wybierz opcję **Utwórz nową automatyzację procesu**, a następnie wybierz opcję **Automatyzacja prognoz przepływów pieniężnych** w menu rozwijanym **Typ harmonogramu**. Należy określić harmonogram dla każdej firmy, dla której aktualizowane są dane prognozy przepływów pieniężnych.  Ta strona pokazuje również oczekujące zadania automatyzacji prognozy przepływów pieniężnych oraz zakończenie ostatniego zadania.  

> [!NOTE] 
> Jeśli istniejące zadania wsadowe są już zaplanowane dla prognoz przepływów pieniężnych, zostanie wyświetlony komunikat o błędzie i nie będzie możliwe włączenie tej funkcji. Istniejące zadania wsadowe będą musiały zostać wyczyszczone, aby można było włączyć tę funkcję. 

Aby uzyskać więcej informacji, zobacz [Automatyzacja procesu](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

### <a name="reporting"></a>Raportowania

Po obliczeniu prognozy przepływów pieniężnych należy odświeżyć informacje skojarzonej jednostki dla sprawozdawczości analitycznej. Na stronie **Magazyn jednostek** zaznacz miarę agregacji **LedgerCovLiquidityMeasurement** i kliknij przycisk **Odśwież**.

Istnieją dwa obszary robocze zawierające dane prognozowania przepływów pieniężnych. Jeden obszar roboczy zawiera dane wszystkich firm, a drugi zawiera dane tylko dla bieżącej firmy.

Dostęp do obszaru roboczego wszystkich firm jest kontrolowany za pomocą obowiązku **Wyświetlanie obszaru roboczego przepływów pieniężnych wszystkich firm**. Domyślnie obszar roboczy **Przegląd środków pieniężnych — wszystkie firmy** jest dostępny dla następujących ról:

- Dyrektor naczelny
- Dyrektor finansowy
- Kontroler finansowy

Dostęp do obszaru roboczego bieżącej firmy jest kontrolowany za pomocą obowiązku **Wyświetlanie obszaru roboczego przepływów pieniężnych bieżącej firmy**. Domyślnie obszar roboczy **Przegląd środków pieniężnych — bieżąca firma** jest dostępny dla następujących ról:

- Księgowy
- Menedżer ds. księgowania
- Kierownik ds. księgowania
- Menedżer ds. rozrachunków z dostawcami
- Menedżer ds. rozrachunków z odbiorcami

Obszar roboczy **Przegląd środków pieniężnych — wszystkie firmy** pokazuje analizy prognostyczne przepływów pieniężnych w walucie systemowej. Walutę systemową i systemowy typ kursu wymiany, które są używane do analiz, definiuje się na stronie **Parametry systemowe**. Ten obszar roboczy zawiera przegląd prognozowania przepływów pieniężnych i sald kont bankowych dla wszystkich firm. Wykres przychodów i rozchodów gotówkowych obrazuje przyszłe przepływy pieniężne i salda w walucie systemowej oraz dostarcza szczegółowych informacji o prognozowanych transakcjach. Widać także prognozowane salda w walutach.

Obszar roboczy **Przegląd środków pieniężnych — bieżąca firma** przedstawia analizy prognostyczne przepływów pieniężnych w walucie rozliczeniowej zdefiniowanej dla firmy. Walutę rozliczeniową używaną do analiz definiuje się na stronie **Księga**. Ten obszar roboczy zawiera przegląd prognozowania przepływów pieniężnych i sald kont bankowych dla bieżącej firmy. Wykres przychodów i rozchodów gotówkowych obrazuje przyszłe przepływy pieniężne i salda w walucie rozliczeniowej oraz dostarcza szczegółowych informacji o prognozowanych transakcjach. Widać także prognozowane salda w walutach.

Aby uzyskać więcej informacji na temat analiz prognostycznych przepływów pieniężnych, zobacz [Przegląd środków pieniężnych — zawartość usługi Power BI](Cash-Overview-Power-BI-content.md).

Ponadto można wyświetlać dane prognozowania przepływów pieniężnych dla określonych kont, zamówień i towarów na następujących stronach:

- **Bilans próbny**: opcja **Prognozy przepływów pieniężnych** pozwala obejrzeć przyszłe przepływy pieniężne dla wybranego konta głównego.
- **Wszystkie zamówienia sprzedaży**: na karcie **Faktura** opcja **Prognozy przepływów pieniężnych** pozwala obejrzeć prognozowane skutki gotówkowe wybranego zamówienia sprzedaży.
- **Wszystkie zamówienia zakupu**: na karcie **Faktura** opcja **Prognozy przepływów pieniężnych** pozwala obejrzeć prognozowane skutki gotówkowe wybranego zamówienia zakupu.
- **Prognoza dostaw**: opcja **Prognozy przepływów pieniężnych** pozwala obejrzeć przyszłe przepływy pieniężne skojarzone z prognozą dostaw wybranego towaru.
- **Prognoza popytu**: opcja **Prognozy przepływów pieniężnych** pozwala obejrzeć przyszłe przepływy pieniężne skojarzone z prognozą popytu na wybrany towar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

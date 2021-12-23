---
title: Omówienie zarządzania świadczeniami
description: Ten temat zawiera omówienie funkcji zarządzania świadczeniami w programie Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dc06fd2ef4992b4ef2e20ace4f5c6bcc0bffb9d2
ms.sourcegitcommit: e06b7d4de6d5ee7ae491d437d6c0365608a5380b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892509"
---
# <a name="benefits-management-overview"></a>Omówienie zarządzania świadczeniami

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników. Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą. Funkcja Zarządzanie świadczeniami dostępna w Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń. Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.

- Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw. Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.
- Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.
- Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.
- Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.
- Przetwarzanie kwalifikowanych zdarzeń życiowych obsługuje przyszłe zdarzenia życiowe.

Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.

> [!NOTE]
> Teraz możesz dostosować strony zarządzania świadczeniami. Do strony **Opcja zapotrzebowania** planów świadczeń można dodawać niestandardowe pola związane ze stawkami za objęcie świadczeniami. Aby uzyskać więcej informacji na temat korzystania z pól niestandardowych, zobacz temat [Pola niestandardowe](hr-developer-custom-fields.md).
>
> ![Niestandardowe pola zarządzania świadczeniami](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Włączanie obszaru roboczego Zarządzanie świadczeniami

Ten temat opisuje sposób włączania funkcji w wersji zapoznawczej w module Human Resources. Wyjaśnia również, które istniejące funkcje w Human Resources są zastępowane przez zarządzanie korzyściami i które funkcje są wyłączone po włączeniu zarządzania korzyściami.

> [!IMPORTANT]
> Po włączeniu Zarządzania świadczeniami w środowisku **Produkcyjnym** nie można go wyłączyć. Zaleca się włączanie i testowanie Zarządzania świadczeniami w środowisku **Piaskownicy** przed włączeniem go w środowisku **Produkcyjnym**. Istnieją znaczne różnice między funkcjami starszego świadczenia i nowymi funkcjami zarządzania świadczeniami, które wymagają dodatkowej konfiguracji i powinny być testowane przed wprowadzeniem do produkcji.

Aby uzyskać więcej informacji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

## <a name="process-overview"></a>Przegląd procesu

Proces konfigurowania korzyści obejmuje następujące zadania:

1.  Skonfiguruj wymagane informacje o korzyściach.
2.  Skonfiguruj opcjonalne informacje o korzyściach.
3.  Konfigurowanie planów świadczeń.
4.  Konfigurowanie elastycznych programów kredytów (opcjonalne).
5.  Skonfiguruj wymagane informacje o pracowniku.
6.  Skonfiguruj opcjonalne informacje o pracowniku.
7.  Przetwarzaj pracowników, aby określić uprawnienia.
8.  Pracownicy wybierają plany za pośrednictwem samoobsługi pracowników (opcjonalnie).
9.  Potwierdź wybór planu pracownika.
10. Przetwarzanie zmiany sytuacji życiowej (opcjonalne).
11. Aktualizacje stawek (opcjonalnie).

## <a name="set-up-required-benefit-information"></a>Skonfiguruj wymagane informacje o korzyściach

Zanim pracownicy będą mogli zostać zarejestrowani w planach, należy skonfigurować wiele komponentów:

- **Parametry zarządzania świadczeniami** — te ustawienia są współużytkowane przez firmy. Możesz ustawić domyślne kody przyczyn, włączyć opcję **Roczne wynagrodzenie z tytułu świadczenia**, ustawić domyślną częstotliwość płatności dla nowych pracowników i włączyć wydarzenia z życia. Aby uzyskać więcej informacji, zajrzyj do omówienia [Ustaw parametry Zarządzania świadczeniami](hr-benefits-setup-parameters.md).
- **Opcje kwalifikowalności kontaktów osobistych** — kontakty osobiste to osoby, które będą na utrzymaniu lub beneficjentami skonfigurowanych planów. Zazwyczaj są to dzieci, małżonkowie lub organizacje powiernicze. Aby uzyskać więcej informacji, zobacz [Konfigurowanie opcji uprawnień do kontaktu osobistego](hr-benefits-setup-contact-eligibility-options.md).
- **Opcje pokrycia** — konfigurowanie typów pokrycia, które będą dostępne dla planu. W szczególności określ, kto powinien być objęty ubezpieczeniem lub jaki zakres jest dostępny. Aby uzyskać więcej informacji, zobacz [Utwórz obcje pokrycia świadczeń](hr-benefits-setup-coverage-options.md).
- **Typy planów** — Skonfiguruj typy planów, które będą dostępne podczas tworzenia planu świadczeń. Przykłady typów planów to **stomatologiczne**, **okulistyczne** i **oszczędnościowe**. Niektóre ważne ustawienia typu planu określają ustawienia dostępne w planie świadczeń. Aby uzyskać więcej informacji, zobacz [Tworzenie typów planów](hr-benefits-setup-plan-types.md).
- **Reguły kwalifikacji** – Reguły kwalifikacji służą do określenia, czy pracownicy kwalifikują się do planu. Z każdym programem świadczeń musi być powiązana co najmniej jedna reguła kwalifikacji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie reguł i opcji uprawnień](hr-benefits-setup-eligibility-rules.md).
- **Częstotliwości płatności** — częstotliwości płatności są wymagane, gdy skonfigurowane są stawki świadczeń. Częstotliwość płatności stosowana w stawce pomaga określić kwotę, jaką pracownik i/lub pracodawca jest winien tygodniowo, miesięcznie lub rocznie. Aby uzyskać więcej informacji, zobacz [Ustaw częstotliwości płatności](hr-benefits-setup-payment-frequencies.md).
- **Stawki** – Stawki określają, ile zasiłek będzie kosztował pracownika lub pracodawcę. Jeśli pieniądze powinny zostać zwrócone pracownikowi (na przykład kredyt na członkostwo w siłowni), wprowadzana jest ujemna stawka. Aby uzyskać więcej informacji, zobacz temat [Konfiguracja stawek](hr-benefits-setup-rates.md).
- **Stawki poziomów** — Stawki poziomów są używane, gdy stawka musi się zmienić na podstawie pewnych kryteriów. Najpopularniejszy poziom to pojedynczy poziom oparty na wieku. Można jednak również ustawić stawki dwupoziomowe, w których stawka może się zmieniać w zależności od płci, wieku lub innych kryteriów.
- **Potrącenia** — Potrącenia to w zasadzie informacje/kody nagłówka, które zostaną przekazane do systemu płacowego w celu zidentyfikowania potrącenia dla świadczenia. Musisz skonfigurować te potrącenia, ponieważ będą one wymagane w planie świadczeń. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie potrąceń](hr-benefits-setup-deductions.md).
- **Okresy świadczeń** — okres świadczenia to okres, w którym pracownicy będą mieli świadczenia z ubezpieczenia. Jest również znany jako plan roczny. Tutaj ustawia się również otwarte okresy zapisów.

## <a name="set-up-optional-benefit-information"></a>Skonfiguruj opcjonalne informacje o korzyściach

Aby utworzyć plan świadczeń, nie trzeba konfigurować następujących składników:

- **Programy** — program to zestaw świadczeń, które podlegają tym samym regułom uprawnień. Na przykład każdy w dziale sprzedaży może otrzymać telefon komórkowy.
- **Pakiety** – Pakiet to grupa korzyści, w której jeden plan musi zostać wybrany, zanim będzie dostępna opcja wyboru dodatkowych planów. Na przykład plan medyczny z wysokim odliczeniem może być połączony z planem konta oszczędnościowego (HSA).
- **Typy zdarzeń życiowych** — zdarzenia dotyczące życia to zdarzenia, które umożliwiają zmianę zasięgu pracownika. Typy zdarzeń z życia są powiązane z typem planu. Na przykład typ planu medycznego może zezwalać na zmiany planów z powodu narodzin lub adopcji albo ze względu na zmianę stanu cywilnego. Jednak typ planu ubezpieczeniowego może nie zezwalać na żadne zmiany z powodu zdarzeń życiowych. Aby uzyskać więcej informacji, zobacz [Skonfiguruj typy wydarzeń z życia](hr-benefits-setup-life-event-types.md).
- **Dni oczekiwania i okresy oczekiwania** — okres oczekiwania na pokrycie ekscesu można ustawić w planie świadczeń. Na przykład nowo zatrudniony pracownik może być w stanie zapisać się na 401(k) dopiero po trzech miesiącach zatrudnienia. W tym przypadku okres oczekiwania wynosi trzy miesiące. Dni oczekiwania są używane w okresie oczekiwania, jeśli nowe zapisy mogą zostać przetworzone i przesłane do dostawcy tylko w określony dzień miesiąca. Na przykład, jeśli zapisy 401(k) mogą być przetwarzane dopiero piętnastego dnia miesiąca, po trzech miesiącach zatrudnienia, ustawiony okres oczekiwania wynosi trzy miesiące, a dzień oczekiwania to piętnasty dzień. Aby uzyskać więcej informacji, zobacz [Konfigurowanie dni oczekiwania](hr-benefits-setup-waiting-days.md) i [Skonfiguruj okresy oczekiwania](hr-benefits-setup-waiting-periods.md).
- **Kody przyczyn** — Kody przyczyn służą do wyjaśnienia, dlaczego świadczenie może się zmienić dla pracownika. Aby uzyskać więcej informacji, zobacz [Konfigurowanie kodów przyczyn](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Konfigurowanie planów świadczeń

Podczas konfigurowania planu świadczeń należy wykonać następujące kroki, zanim pracownicy będą mogli zostać zarejestrowani:

- Przypisywanie okresu świadczenia.
- Dołącz opcje objęcia świadczeniem.
- Ustaw datę ważności i prawidłową na **karcie Ogólne**.
- Przypisz co najmniej jedną regułę uprawnień.
- Ustaw **pole Zezwalaj/Kontynuuj rejestrację** na **karcie Ustawienia**.

Aby uzyskać więcej informacji na temat konfigurowania planów świadczeń, zobacz [Konfigurowanie planów świadczeń](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Konfigurowanie elastycznych programów kredytów (opcjonalne)

Za pomocą programów kredytu elastycznego można rejestrować pracowników na świadczenia zgodnie z ustaloną wcześniej liczbą elastycznych punktów kredytowych. Pracownicy mogą wybrać sposób przydzielania ich elastycznych punktów kredytowych. Na przykład, jeśli pracownicy są już objęci ubezpieczeniem zdrowotnym współmałżonka, nie muszą wykorzystywać swoich kredytów na ubezpieczenie zdrowotne. Dlatego mogą zamiast tego chcieć wykorzystać je do innych korzyści. Aby uzyskać więcej informacji na temat programów kredytów elastycznych, zobacz [Konfigurowanie programów kredytów elastycznych](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Skonfiguruj wymagane informacje o pracowniku

Aby można było zarejestrować pracowników w ramach świadczeń, musisz podać wymagane informacje dla nich. 

Pracownik musi mieć przypisane **stanowisko**. **Stanowisko** można przypisać do pracownika na stronach **Pracownik** lub **Stanowisko** aktualizując **przypisanie pracownika**. 

Następnie należy zarejestrować pracowników w stałym planie wynagrodzeń w dniu ich rozpoczęcia lub muszą mieć **roczną kwotę wynagrodzenia zasiłkowego**. Przed przypisaniem **stałego wynagrodzenia** do pracownika etatowego musi być przypisane **stanowisko**. 

> [!NOTE] 
> **Data rozpoczęcia dla stałego wynagrodzenia** nie może być wcześniejsza niż **data przypisania stanowiska**.

Alternatywnie, jeśli użytkownik ma pracownika, który otrzymuje dodatkowe wynagrodzenie, na przykład prowizje, może dodać kwotę **Świadczenia do wynagrodzenia rocznego** z rekordu pracownika etatowego. Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty **Roczne wynagrodzenie z tytułu świadczenia** będzie używana kwota **Stałe roczne wynagrodzenie**. **Świadczenia do wynagrodzenia rocznego** musi być ważne na dzień rozpoczęcia lub początek okresu świadczenia, w zależności od tego, która z nich jest najpóźniejsza. Jednak stanowisko nie musi mieć przypisanego **rocznego wynagrodzenia z tytułu świadczenia**. Aby włączyć funkcję **Roczne wynagrodzenie z tytułu świadczenia** przejdź na stronę **udostępnionych parametrów rozwiązania Human Resources**, na karcie **Zarządzanie świadczeniami**. Ta funkcja jest domyślnie wyłączona.

> [!IMPORTANT]
> Jeżeli dla pracownika zostanie wprowadzone zarówno **stałe wynagrodzenie**, jak i kwota **rocznego wynagrodzenia za świadczenia**, przy określaniu kwot pokrycia będzie się uwzględniać **roczne wynagrodzenie za świadczenia**. W sekcji **Szczegóły zatrudnienia** na stronie **Pracownik** należy wybrać wartość w polu **Częstotliwość wypłaty świadczeń**.

## <a name="configure-optional-employee-information"></a>Skonfiguruj opcjonalne informacje o pracowniku
Podczas tworzenia planu świadczeń, w którym używane są stawki oparte na płci lub wieku, należy wprowadzić datę urodzenia i płeć dla pracownika, aby obliczyć koszty świadczeń.

## <a name="process-employees-to-determine-eligibility"></a>Przetwarzaj pracowników, aby określić uprawnienia
Zanim pracownicy będą mogli zostać zarejestrowani w planach, uruchamiane jest przetwarzanie uprawnień w celu określenia, do których planów są uprawnieni. Wyniki procesu kwalifikowalności można wyświetlić w **przeglądarce wyników procesu**. Aby uzyskać więcej informacji, zobacz [Przetwarzanie uprawnień do rejestracji](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Pracownicy wybierają plany przy użyciu funkcji **Samoobsługa pracownika etatowego** (opcjonalnie)

Gdy nastąpi otwarta rejestracja, pracownicy są nowo zatrudnieni lub ma miejsce wydarzenie życiowe, pracownicy mogą wybierać lub aktualizować swoje świadczenia za pośrednictwem **samoobsługi pracownika etatowego**. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Skonfiguruj samoobsługę pracownika](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Potwierdź wybór planu pracownika

Wybrane przez pracowników świadczenia muszą zostać potwierdzone, zanim pracownicy zostaną uznani za w nich zapisanych. Świadczenia można również wybrać w imieniu pracownika. Aby wybrać lub potwierdzić świadczenia, na **stronie Pracownik** na karcie **Świadczenia** wybierz pozycję **Plany świadczeń dla pracowników**. Aby wybrać lub potwierdzić korzyści dla wielu pracowników, użyj strony **zbiorczej aktualizacji Planów świadczeń pracownika**.

## <a name="life-event-processing-optional"></a>Przetwarzanie zmiany sytuacji życiowej (opcjonalne)

W cyklu życia pracownika każdy pracownik może doświadczyć różnych wydarzeń życiowych, takich jak małżeństwo, zmiany w zatrudnieniu lub zmiany osób na utrzymaniu lub beneficjentów. Aby używać zdarzeń życia, należy je włączyć na **stronie udostępnionych parametrów rozwiązania Human Resources**. Skonfiguruj typy wydarzeń z życia i opcje wydarzeń z życia dla typów planów.

Aby móc przetwarzać zdarzenia z życia, musisz przeprowadzić otwartą rejestrację co najmniej raz w okresie zatrudnienia. W Stanach Zjednoczonych otwarta rejestracja zazwyczaj odbywa się raz na rok. Poza Stanami Zjednoczonymi otwarta rejestracja może być wykonywana w momencie zatrudniania. Przetwarzanie zdarzeń z życia nie wymaga, aby pracownicy wybierali plan świadczeń. Jednak pracownicy musieli zostać uwzględnieni w otwartym przetwarzaniu zapisów. Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Przetwarzanie zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-events.md)
- [Przetwarzanie zmian zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-event-changes.md)
- [Przetwarzanie uprawnień zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>Aktualizacje stawek (opcjonalnie)

Czasami stawka świadczenia zmienia się w okresie obowiązywania planu. Aby zaktualizować stawki dla pracowników, którzy są już zarejestrowani w planie, musisz przetworzyć zmiany stawek. Aby uzyskać więcej informacji, zobacz [Przetwarzanie zmian stawek](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

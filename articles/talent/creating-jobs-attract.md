---
title: Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract
description: "W tym temacie opisano elementy funkcji w aplikacji Attract. Ponadto wyjaśniono, jak utworzyć funkcję."
author: josaw
manager: AnnBe
ms.date: 10/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: af945042c150fff1a95cdb046f2a712cb2c2c061
ms.contentlocale: pl-pl
ms.lasthandoff: 10/24/2018

---

# <a name="create-approve-and-post-jobs-in-attract"></a>Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract

[!include [banner](includes/banner.md)]

W tym temacie opisano elementy funkcji w aplikacji Microsoft Dynamics 365 for Talent Attract. Ponadto wyjaśniono, jak utworzyć funkcję.

## <a name="job-creation"></a>Tworzenie funkcji

Administratorzy, osoby rekrutujące i menedżerowie zatrudniający mogą tworzyć funkcje. Podczas tworzenia funkcji jest wyświetlany monit o wybranie swojej roli w procesie: menedżera zatrudniającego lub osoby rekrutującej. Po wybraniu roli zostanie wyświetlony monit o wybranie szablonu procesu. W przypadku wybrania opcji **Pomiń** jest używany szablon domyślny. Aby uzyskać więcej informacji o szablonach procesów, zobacz [Tworzenie szablonu procesu w aplikacji Attract](./process-templates-attract.md).

Funkcja w aplikacji Attract zawiera szczegóły funkcji, zespół rekrutacyjny, proces rekrutacji, oferty pracy i analizy.

## <a name="job-details"></a>Szczegóły funkcji

Karta **Szczegóły funkcji** zawiera szczegółowe informacje o obowiązkach w funkcji i atrybutach funkcji. Pola nazwy funkcji, opisu funkcji i lokalizacji funkcji są wymagane. Pozostałe pola są opcjonalne.

Domyślnie pole **Liczba wolnych posad** jest ustawione na **1**. Można jednak zmienić jego wartość. Po przygotowaniu oferty na funkcję wartość pola **Liczba dostępnych wolnych posad** jest zmniejszana.

Jeśli w Centrum administracyjnym włączono funkcję zarządzanie stanowiska, jest dostępna opcja wyszukiwania **Aktualizuj stanowiska**. Funkcja wyszukiwania odczytuje jednostkę JobPosition w usłudze Common Data Service dla aplikacji i zwraca listę stanowisk, które można wybrać dla funkcji. Jeśli wybrana liczba stanowisk przekracza liczbę otwartych stanowisk, pojawi się ostrzeżenie. Otrzymasz również ostrzeżenie, jeśli stanowisko jest używane w wielu funkcjach.

> [!NOTE]
> Funkcja zarządzania stanowiskami jest dostępna po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

W zależności od ustawień w działaniu Oferta w procesie rekrutacji ten sam numer stanowiska może zostać użyty dwa razy w ofercie. Aby uzyskać więcej informacji, zobacz [Proces zatrudniania](./activities-attract.md).

Aplikacja Attract zawiera domyślny zestaw **umiejętności**. Te umiejętności są wyświetlane jako sugestie podczas wpisywania tekstu. Możesz dodać więcej umiejętności, wprowadzając treść nowej umiejętności w polu, a następnie naciskając klawisz Enter.

Aplikacja Attract zawiera domyślny zestaw **czynności związanych z funkcjami**. Można dodać maksymalnie trzy kolejne czynności związane z funkcją, wprowadzając nową czynność w polu, a następnie naciskając klawisz Enter.

Aplikacja Attract zawiera domyślny zestaw **branż firmy**. Można dodać maksymalnie trzy kolejne branże firmy, wprowadzając nową branżę firmy w polu, a następnie naciskając klawisz Enter.

## <a name="hiring-team"></a>Zespół rekrutacyjny

Karta **Zespół rekrutacyjny** zawiera listę osób, które będą zaangażowane w funkcję. Gdy użytkownicy są dodawani do zespołu rekrutacyjnego, trzeba im przypisać rolę w zespole rekrutacyjnym. Rola określa dane, do których użytkownicy będą mieli dostęp, oraz powiadomienia, które będą otrzymywać. Role, które można wybrać, to **Osoba rekrutująca**, **Menedżer zatrudniający**, **Pełnomocnik** i **Osoba przeprowadzająca rozmowę kwalifikacyjną**. Aby uzyskać więcej informacji o uprawnieniach w rolach, zobacz dokument „Zarządzanie rolami”. Osoby rekrutujące i menedżerowie zatrudniający mogą wyznaczyć jednego lub więcej pełnomocników do pracy w ich imieniu. Aby uzyskać więcej informacji o użytkownikach delegowanych, zobacz [Zarządzanie zabezpieczeniami i rolami w aplikacji Attract](./security-attract.md).

Zespół rekrutacyjny można zaktualizować po uaktywnieniu funkcji.

## <a name="process"></a>Przetwarzaj

Domyślne informacje o procesie rekrutacji zależą od szablonu procesu wybranego podczas tworzenia funkcji. Jeśli w tamtym momencie nie wybrano konkretnego szablonu, będzie używany domyślny szablon. Podczas definiowania procesu rekrutacji można dodawać i usuwać różne etapy z wyjątkiem etapów Prospekt, Zgłoszenie i Oferta. Chociaż etapu Prospekt nie da się usunąć, można go wyłączyć. Na każdym etapie można dodać lub usunąć jedno lub więcej wstępnie zdefiniowanych działań.

Aby uzyskać więcej informacji o działaniach, które można dodawać do procesu rekrutacji, zobacz [Działania w ramach procesu zatrudniania w aplikacji Attract](./activities-attract.md).

> [!NOTE]
> Procesu rekrutacji nie można zaktualizować po uaktywnieniu funkcji.

## <a name="postings"></a>Księgowania

Po uaktywnieniu funkcji można ją opublikować. Tylko osoby rekrutujące i menedżerowie zatrudniający mogą publikować funkcje. Funkcję można opublikować w witrynie Talent Careers (witrynie rozwoju kariery wewnątrz aplikacji Microsoft Dynamics 365 for Talent) lub serwisie LinkedIn. Zespół aplikacji Attract stale pracuje nad dodawaniem agregatorów ogłoszeń o pracę. W związku z tym ta lista będzie regularnie poszerzana.

Aby uzyskać więcej informacji o ofertach pracy, zobacz [Funkcjonalność witryny rozwoju kariery w aplikacji Attract](./career-site.md).

> [!NOTE]
> Funkcjonalność ofert pracy jest dostępna tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji dla aplikacji Attract.

## <a name="activate"></a>Uaktywnianie

Po uaktywnieniu funkcji można ją opublikować oraz dodawać do niej prospektów i kandydatów. Opcję dodawania prospektów do funkcji ustawia się w działaniu Prospekt w procesie rekrutacji.

> [!NOTE]
> Procesu rekrutacji nie można zaktualizować po uaktywnieniu funkcji.

## <a name="prospects-and-applicants"></a>Prospekci i kandydaci

Opcję dodawania prospektów do funkcji ustawia się w [działaniu Prospekt](./activities-attract.md#prospect-activity) w procesie rekrutacji. Tę opcję należy ustawić przed uaktywnieniem funkcji. Po uaktywnieniu funkcji można do niej dodawać prospektów i kandydatów.

## <a name="approvals"></a>Zatwierdzenia

Funkcje w aplikacji Attract można przesyłać do zatwierdzenia. Nie wszystkie funkcje wymagają zatwierdzenia. Wymóg ustawia się na poziomie szablonu. Domyślnie zatwierdzenia są wyłączone w szablonie. Aby skonfigurować zatwierdzanie, przejdź do szablonu procesu i w polu **Zatwierdzenie** ustaw wartość Domyślnie. Następnie wybierz ten szablon podczas tworzenia funkcji.

Po zapisaniu funkcji można ją przesłać do zatwierdzenia. W poniższej tabeli wymieniono stany dokumentu używającego zatwierdzeń.

| Stan   | Stanowy                                                               |
|----------|---------------------------------------------------------------------|
| Robocza    | Funkcja została zapisana, ale nie przesłana do przepływu pracy. |
| Oczekujący  | Funkcja została przesłana do osób zatwierdzających.                            |
| Zatwierdzona | Funkcja została zatwierdzona, ale jeszcze nie uaktywniona.            |
| Odrzucona | Funkcja została odrzucona i nie można jej aktywować.               |
| Aktywne   | Funkcja została zatwierdzona i uaktywniona.                            |

Na liście funkcji można filtrować według stanów funkcji.

Zatwierdzenia mogą być wysyłane do dowolnego użytkownika usługi Microsoft Azure Active Directory (Azure AD) w firmie. Zatwierdzenia są wysyłane jednocześnie do wszystkich osób wyszczególnionych jako osoby zatwierdzające. Po zatwierdzeniu funkcji można ją aktywować.

Osoby wyświetlane jako osoby zatwierdzające otrzymają powiadomienie w aplikacji Attract informujące, że mają pozycję do zatwierdzenia. Pozycja do zatwierdzenia pojawi się także w sekcji **Przypisane do Ciebie** na pulpicie nawigacyjnym. Gdy ktoś zaakceptuje lub zatwierdzi funkcję, zespół rekrutacyjny otrzyma powiadomienie. Na koniec zespół rekrutacyjny otrzyma powiadomienie po zatwierdzeniu funkcji.

## <a name="create-a-job"></a>Tworzenie stanowiska

Aby utworzyć funkcję, należy wykonać poniższe kroki.

1. Przejdź do okna **Funkcje**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa funkcji** wprowadź nazwę funkcji. W polu **Rola** wprowadź swoją rolę.
4. W polu **Szablon** wybierz szablon. Alternatywnie wybierz opcję **Pomiń**. W przypadku wybrania opcji **Pomiń** będzie używany szablon oznaczony jako domyślny.

    Jeśli dokument powinien przejść przez proces zatwierdzania, wybierz szablon, który w polu **Proces zatwierdzania** ma ustawioną wartość **Domyślnie**.

5. Na karcie **Szczegóły** wprowadź szczegóły funkcji. Pola **Tytuł**, **Opis funkcji** i **Lokalizacja** są wymagane.
6. Wybierz opcję **Zapisz**.
7. Na karcie **Zespół rekrutacyjny** dodaj menedżera zatrudniającego, osobę rekrutującą lub osobę przeprowadzającą rozmowę kwalifikacyjną.
8. Wybierz opcję **Zapisz**.
9. Na karcie **Proces** dodaj lub usuń etapy zgodnie z potrzebami:

    - Aby dodać etap, wybierz opcję **+ Nowy etap**.
    - Aby usunąć etap, umieść nad nim wskaźnik myszy, a następnie kliknij wyświetloną ikonę kosza.

        > [!NOTE]
        > Nie można usunąć etapów Prospekt, Zgłoszenie ani Oferta.

10. Dodaj lub usuń działania zgodnie z potrzebami:

    - Aby dodać działanie, przeciągnij je z listy po prawej stronie do odpowiedniego etapu. Alternatywnie kliknij dwukrotnie działanie, a następnie wybierz etap, do którego chcesz je dodać.
    - Aby usunąć działanie, rozwiń je, a następnie kliknij przycisk kosza w nagłówku działania.

11. Wybierz opcję **Zapisz**.
12. Jeśli wybrano opcję używania procesu zatwierdzania, wykonaj następujące kroki:

    1. Kliknij przycisk **+ Dodaj osobę zatwierdzającą**, a następnie wprowadź nazwę użytkownika mającego konto w usłudze Azure AD. Można dodać wiele osób zatwierdzających.
    2. Kliknij przycisk **Wyślij do osób zatwierdzających**.

    W polu **Stan funkcji** jest ustawiona wartość **Oczekująca**. Gdy wartość w polu **Stan funkcji** zmieni się na **Zatwierdzona**, można uaktywnić funkcję.

13. Aby aktywować funkcję, wybierz opcję **Aktywuj**.
14. Aby opublikować funkcję, przejdź do okna **Oferty**, a następnie wybierz opcję **Opublikuj teraz** w sekcji witryny Talent Carriers lub serwisu LinkedIn.


---
title: Przegląd obsługi relacji z klientami
description: Ten temat zawiera omówienie nowych możliwości relacji z klientami dostępnych w aplikacji sklepu.
author: bebeale
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260624"
- intro-internal
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 598145bccadbeb44d33adb96388f6af5a8a45f5d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352695"
---
# <a name="clienteling-overview"></a>Omówienie obsługi relacji z klientami

[!include [banner](includes/banner.md)]


Wielu sprzedawców detalicznych, w szczególności najlepszych specjalistycznych sprzedawców detalicznych, chce, aby ich sprzedaż była oparta na formie długoterminowych relacji z klientami. Pracownicy powinni wiedzieć o upodobaniach tych klientów, historii zakupów, preferencjach dotyczących produktów oraz ważnych datach, takich jak rocznice i urodziny. Sprzedawcy muszą mieć miejsce, w którym mogą przechwytywać te informacje i łatwo znajdować je w razie potrzeby. Jeśli te informacje są dostępne w jednym widoku, klienci mogą łatwo kierować klientów, którzy spełniają określone kryteria. Na przykład mogą znaleźć wszystkich klientów, którzy preferują kupować torebki, lub odbiorców, którzy mają ważne zdarzenia, takie jak urodziny czy rocznice.

## <a name="client-book"></a>Książka adresowa klientów

W Microsoft Dynamics 365 Commerce detaliści mogą korzystać z funkcji księgi klientów, aby pomóc współpracownikom w nawiązywaniu długoterminowych relacji z kluczowymi klientami.

W książce klienta znajdują się karty odbiorców pokazujące informacje kontaktowe dla każdego klienta wraz z trzema dodatkowymi właściwościami zdefiniowanymi przez sprzedawcę i skonfigurowanymi w programie Headquarters. Detaliści mogą podjąć decyzję o trzech najważniejszych kwestiach, jakie pracownicy muszą znać w przypadku klientów. Na przykład sprzedawca biżuterii może chcieć podać ważne daty, takie jak rocznice lub urodziny, ponieważ są to sytuacje, w których ludzie mogą kupić więcej biżuterii. Podobnie sprzedawca odzieży może chcieć uwzględnić preferencje i marki klientów dotyczące zakupów.

Książka klienta pozwala również pracownikom działu sprzedaży filtrować listę, aby wyświetlać tylko klientów spełniających określone kryteria. Na przykład w sklepie pojawiła się nowa kolekcja butów, a współpracownik chce poinformować klientów, którzy lubią kupować buty. W takim przypadku pracownik może przefiltrować książkę klientów, aby znaleźć odpowiednich klientów, a następnie podjąć dalsze działania.

Jeśli z jakiegoś powodu klienci nie są już uważani za kluczowych klientów i dlatego nie powinni być ściśle zarządzani, sprzedawcy mogą usunąć ich z księgi klientów.

Niektórzy detaliści nie chcą zarządzać klientami na poziomie partnera handlowego. Zamiast tego chcą zarządzać listą najważniejszych klientów na poziomie sklepu. Detaliści mogą przeglądać odbiorców z książek klientów sklepów. Za pomocą tej opcji detaliści mogą przeglądać odbiorców z ksiąg klientów wszystkich jednostek sprzedaży, których książka adresowa jest zgodna z książką adresową bieżącego sklepu. W ten sposób, jeśli jednostka stowarzyszona działa w wielu sklepach podmiotu prawnego, w książce klientów wyświetlani są klienci ze wszystkich tych sklepów. Ta funkcja obsługuje dodatkowe funkcje. Na przykład odbiorca może zostać ponownie przypisany od jednego sprzedawcy do innego. Ta funkcja jest przydatna, gdy pracownicy zostają przeniesieni lub opuszczają firmę.

Każdy przedstawiciel handlowy może mieć jedną księgę klienta na osobę prawną, a współpracownicy mogą dodawać jednego lub więcej klientów do swojej księgi klientów. W Commerce każdy klient może być obecnie dodany tylko do jednej księgi klienta. Jednak firma Microsoft planuje dodanie funkcji pozwalającej na dodanie jednego klienta do wielu ksiąg klientów.

> [!NOTE]
> W przeciwieństwie do wyszukiwania klientów książka klienta nie filtruje rekordów klientów na podstawie książek adresowych sklepu.

## <a name="activities-and-notes"></a>Działania i notatki

Kanały online umożliwiają sprzedawcom zapoznanie się z preferencjami klientów bez konieczności wyraźnego podawania tych informacji przez klientów. Natomiast gdy klienci wchodzą w interakcje ze sprzedawcami w sklepie, wyraźnie dzielą się informacjami o swoich preferencjach. Niestety, informacje te mogą zostać utracone po zakończeniu sprzedaży. Jednak zapisanie tych informacji może pomóc detalistom lepiej zrozumieć klientów, a tym samym pomóc im w dostarczaniu lepszych rekomendacji i lepszych ogólnych wrażeń z zakupów.

W celu przechwycenia informacji krytycznych udostępnianych przez klientów, pracownicy mogą używać nie tylko atrybutów książki klienta, ale również używają funkcji działania i uwagi. Detaliści mogą konfigurować typy działań, takie jak informacje o odwiedzaniu sklepu, adres e-mail, numer telefonu i terminy. Działania, które tworzy skojarzenie, można wyświetlać w formacie osi czasu w punkt sprzedaży (POS). Można je również przejrzeć na karcie **Działania** na stronie **Wszyscy klienci \> Ogólne** w Headquarters.

Pracownicy działu sprzedaży mogą również wykorzystywać notatki do przechwytywania ogólnych informacji o klientach, do których można się odwoływać przed każdą interakcją. Te notatki są zapisywane w programie Headquarters i mogą być wyświetlane w profilu klienta lub na stronie szczegółów klienta w serwisie telefonicznym.

> [!NOTE]
> Obecnie wszystkie notatki i działania mogą być przeglądane przez dowolnego sprzedawcę, który pracuje dla firmy i mogą wyświetlać strony szczegółów klientów. Notatki i działania nie są ograniczone do sprzedawcy, który dodał klienta do księgi klienta.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integracja z programem Dynamics 365 Customer Insights

Za pomocą aplikacji Dynamics 365 Customer Insights detaliści mogą agregować dane z różnych systemów używanych przez klientów do współpracy z marką detaliczną. Następnie mogą wykorzystać te dane do wygenerowania pojedynczego widoku klienta i uzyskania szczegółowych informacji. Integracja Customer Insights z Commerce umożliwia wybranie jednego lub większej liczby miar, które powinny być przedstawione w kartotece klienta w książce klienta. Na przykład Detaliści mogą skorzystać z danych w usłudze Customer Insights, aby obliczyć „prawdopodobieństwo zmian” dla klienta i zdefiniować „następną najlepszą akcję” Jeśli te wartości są zdefiniowane jako miary, mogą być wyświetlane w kartotece klienta i mogą zawierać kluczowe informacje dla sprzedawców. Aby uzyskać więcej informacji o Customer Insights, zobacz dokumentację [Dynamics 365 Customer Insights](/dynamics365/ai/customer-insights/overview). Aby uzyskać więcej informacji o tej funkcji, zobacz: [Miary](/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Ustawianie relacji z klientami

Aby włączyć funkcję relacji z klientami w środowisku, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** Przefiltruj funkcje modułu **handel detaliczny i commerce**.

    ![Relacja z klientami na liście funkcji modułu Commerce.](./media/Enable_clienteling.png "Relacja z klientami na liście funkcji modułu handel detaliczny i moduł Commerce")

2. Włącz funkcję **Relacja z klientami**, zaznaczając opcję **Włącz teraz**.
3. Na stronie **Parametry Commerce** na karcie **sekwencja numerów** wybierz wiersz **identyfikatora księgi klienta**. W polu **kod sekwencji numerów** wybierz kod każdej sekwencji numerów. System użyje tej sekwencji numerów do przypisania identyfikatora do ksiąg klientów.
4. Wybierz opcję **Zapisz**.
5. Utwórz nową grupę atrybutów zawierającą atrybuty, które mają być przechwytywane dla odbiorców, którzy są zarządzani w księgach klientów Zobacz instrukcje w [Atrybuty i grupy atrybutów](./attribute-attributegroups-lifecycle.md).

    - Umożliwia zdefiniowanie wymaganych atrybutów, które **mogą być rafinowane**. Klienci współpracowników mogą następnie wykorzystać te atrybuty do filtrowania swojej księgi klienta.
    - Umożliwia ustawienie kolejności wyświetlania dla tych atrybutów. Ta kolejność wyświetlania decyduje o tym, które atrybuty powinny być pokazywane w kartotece odbiorcy w książce klienta. Kolejność wyświetlania 1 jest traktowana jako większa niż wartość w kolejności wyświetlania równa 2. Dlatego atrybut, który ma kolejność wyświetlania równą 1, będzie wyświetlany przed atrybutem, który ma kolejność wyświetlania równą 2.

    > [!NOTE]
    > Na tej samej stronie możesz udostępnić Customer Insights. Jednak do celów uwierzytelniania musi zostać utworzony identyfikator aplikacji Azure i klucz tajny. (Aby uzyskać informacje o wymaganiach, zapoznaj się z sekcją [Włączanie integracji odbiorcy w Customer Insights z Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) w dalszej części tego tematu.) Jeśli funkcja Customer Insights jest włączona, a użytkownik wybierze jedną lub więcej miar, które powinny być wyświetlone w kartotece klienta, miary te będą najpierw wykazane. Następnie na podstawie kolejności wyświetlania będą pokazywane grupy atrybutów z księgi klienta. Jeśli na przykład zostaną wybrane dwie miary ze Customer Insights, to w kartotece odbiorcy zostaną wyświetlone te dwie miary i jeden atrybut księgowy klienta. (Wyświetlany atrybut księgi klienta będzie atrybutem o najwyższym porządku wyświetlania.)

6. Na stronie **parametry Commerce** na karcie **Relacje z klientem**, w polu **Grupa atrybutów księgi klienta**, wybierz utworzoną właśnie grupę atrybutów.

    ![Wybrana grupa atrybutów księgi.](./media/Client%20book%20attributes.png "Wybrana grupa atrybutów księgi")

7. Aby przechwytywać działania występujące w punkcie sprzedaży, należy zdefiniować typy działań na stronie **typy działań** (**Retail i Commerce \> Klienci \> Typy działań**).

    > [!NOTE]
    > Typy działań są ściągane przez Commerce Scale Unit podczas pierwszego połączenia w czasie rzeczywistym. Po rozpoczęciu działania są one buforowane przez kilka godzin W przypadku zmiany typów działań należy poczekać, aż pamięć podręczna przestanie obowiązywać. Ewentualnie w środowiskach nieprodukcyjnych należy ponownie uruchomić usługę Commerce Scale Unit.

8. Dodaj dwa przyciski do odpowiedniego układu ekranu punktu sprzedaży, aby klienci współpracowników mogli przeglądać własną książkę klientów i księgę klientów sklepów. (Książki klienckie sklepu zawierają klientów ze wszystkich książek adresowych, które współużytkują książkę adresową z sklepem) Odpowiednie operacje mają nazwę **Wyświetlanie odbiorców w książce klientów** i **wyświetlanie odbiorców z książek klientów sklepów**. Dostępne są trzy dodatkowe operacje związane z księgami klientów. Te operacje decydują o tym, którzy użytkownicy mogą dodawać, usuwać i ponownie przypisywać odbiorców z księgi klienta. Są one nazwane **Dodaj odbiorcę do księgi klienta**, **usuwają odbiorców z księgi klienta** i **ponownie przypisują odbiorcy do księgi klienta**.
9. Uruchom następujące zadania harmonogramu dystrybucji: 1040, 1150, 1110 i 1090.

Po zakończeniu tej procedury, pracownicy handlowi mogą otworzyć stronę ze szczegółowymi informacjami o kliencie w punkcie sprzedaży i dodawać klientów do swojej księgi klientów, przeglądać i rejestrować działania i notatki dla klientów oraz kierować klientów za pomocą atrybutów klientów i klientów w celu filtrowania książka klienta. Na poniższe ilustracji pokazano przykład księgi klienta.

![Przykład książki klienta.](./media/client_book.png "Przykład książki klienta")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Włączanie integracji Customer Insights z Commerce

Aby włączyć integrację Customer Insights z Commerce, należy upewnić się, że istnieje aktywne wystąpienie klienta w dzierżawie, w którym jest inicjowana Customer Insights z Commerce. Musisz również mieć konto Azure Active Directory (Azure AD), które ma subskrypcję systemu Azure.

Aby skonfigurować integrację wykonaj następujące czynności:

1. W portalu Azure zarejestruj nową aplikację i zanotuj nazwę aplikacji, jej identyfikator oraz klucz tajny. Te informacje będą używane do uwierzytelniania między usługami między Commerce i Customer Insights. Zwróć uwagę na tajny klucz, ponieważ będzie on wymagany do zapisania go w magazynie kluczy. W poniższym przykładzie użyj CI_Access_name, CI_Access_AppID, CI_Access_Secret odpowiednio dla nazwy aplikacji, identyfikatora aplikacji i klucza tajnego. Aby uzyskać więcej informacji, [Skorzystaj z systemu szybkiego startu: Zarejestruj aplikację na platformie tożsamości Microsoft](/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Należy wykonać odpowiednie kroki, aby pamiętać o zmianie klucza tajnego przed jego wygaśnięciem. W przeciwnym razie integracja zostanie zatrzymana niespodziewanie.

2. Przejdź do instancji Customer Insights i wyszukaj nazwę aplikacji utworzonej powyżej (w tym przykładzie „CI_Access_name”).
3. Utwórz magazyn kluczy platformy Azure i zanotuj nazwę i adres URL (w tym przykładzie „KeyVaultName”, „KeyVaultURL”). Aby uzyskać instrukcje, [Skorzystaj z opcji szybkiego startu: set i Pobierz klucz tajny z magazynu kluczy systemu Azure przy użyciu portalu Azure Portal](/azure/key-vault/quick-create-portal).
4. Zapisz sekret (w tym przykładzie „CI_Access_Secret”) w magazynie. Kiedy ten sekret jest przechowywany w magazynie, otrzymuje nazwę. Zanotuj tajną nazwę (w tym przykładzie „SecretName”).
5. Aby uzyskać dostęp do klucza tajnego z Azure Key Vault, musisz utworzyć inną aplikację z identyfikatorem aplikacji i wpisem tajnym (w tym przykładzie „KeyVault_Access_AppID” i „KeyVault_Access_Secret”). Pamiętaj, że tajny klucz jest bezpieczny, ponieważ nie będzie wyświetlany ponownie.
6. Następnie musisz nadać aplikacji uprawnienia dostępu do Key Vault z Commerce przy użyciu interfejsów API. Przejdź do strony aplikacji w Azure Portal. W sekcji **Zarządzaj** wybierz uprawnienia **Interfejsu API**. Dodaj uprawnienie dostępu do **Klucza systemu Azure**. Dla tego uprawnienia wybierz pozycję **Zasady dostępu**. Wybierz szablon jako **Zarządzanie wpisami tajnymi**, a następnie wybierz opcje **Pobierz**, **Lista**, **Odszyfruj** i **Szyfruj**. 
5. W Commerce headquarters przejdź do **Administrowanie systemem \> Ustawienia \> Parametry usługi Key Vault** i wprowadź wymagane informacje dotyczące magazynu kluczy. Następnie w polu **klient magazynu kluczy** wprowadź identyfikator aplikacji, który został użyty w kroku 4, aby umożliwić Commerce dostęp do kluczy tajnych w magazynie kluczy.
6. Aby dodać aplikację utworzoną w kroku 1 do listy bezpiecznych aplikacji (czasami nazywanych bezpieczną listą), należy przejść do sekcji Customer Insights i wybrać dostęp do **Widoku** aplikacji. Aby uzyskać instrukcje instalacji, zobacz [Uprawnienia](/dynamics365/ai/customer-insights/pm-permissions).
7. Na stronie **Administrowanie systemem > Ustawienia > Parametry Key Vault** w usługach Commerce HQ zaktualizuj pola w sposób opisany poniżej: 

- **Adres URL klucza**: KeyVaultURL (z kroku 3 powyżej).
- **Klient Key Vault**: „KeyVault_Access_AppID” (z kroku 5 powyżej).
- **Wpis tajny Key Vault**: „KeyVault_Access_Secret” (z kroku 5 powyżej).
- W sekcji **Wpisy tajne**:
    - **Nazwa**: dowolna nazwa, na przykład „CISecret”.
    - **Opis**: dowolna wartość.
    - **Wpis tajny**: **vault**://<Name of key vault>/<name of secret>> W tym przykładzie będzie to „vault://KeyVaultName/SecretName”.

Po zaktualizowaniu pól wybierz pozycję **Sprawdzanie** poprawności, aby zagwarantować dostęp do tajnych danych przez aplikację Commerce.

8. W Commerce na stronie **Parametry Commerce** na karcie **Obsługa relacji z klientami** na skróconej karcie **Dynamics 365 Customer Insights** ustaw **Identyfikator aplikacji** „CI_Access_AppID” (z kroku 1 powyżej). W przypadku **Wpisów tajnych** należy wybrać wpis tajny wprowadzony w kroku 7 powyżej („CISecret”). Ustaw **Włącz Customer Insights** ustaw wartość **Tak**. Jeśli konfiguracja z jakiegoś powodu nie powiedzie się, zostanie wyświetlony komunikat o błędzie, a ta opcja zostanie ustawiona na **Nie**. 

W szczegółowym zakresie można mieć wiele środowisk w Customer Insights, np. środowiska testowe i produkcyjne. W polu **identyfikator wystąpienia środowiska** wprowadź odpowiednie środowisko. W polu **alternatywny identyfikator klienta** wprowadź właściwość w Customer Insights, który jest mapowany na konto odbiorcy. (W portalu Commerce numer konta odbiorcy jest identyfikatorem odbiorcy.) Pozostałe trzy właściwości to miary, które będą pokazywane na karcie odbiorcy w księdze klienta. W kartotece odbiorcy można wybrać maksymalnie trzy miary, które mają zostać wyświetlone Nie trzeba jednak wybierać żadnych miar. Jak już kazano wcześniej, system najpierw wyświetla te wartości, a następnie wyświetla wartości dla grupy atrybutów księgi klienta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
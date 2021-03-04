---
title: Ustawianie windykacji
description: Ten artykuł przedstawia sposób konfigurowania funkcji windykacji.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f8e066b1df3eb3a26d488e1c014f4ae3f31395a
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4447019"
---
# <a name="set-up-collections"></a>Ustawianie windykacji

[!include [banner](../includes/banner.md)]

Ten artykuł przedstawia sposób konfigurowania funkcji windykacji. Aby korzystać z funkcji windykacji, należy wykonać kilka kroków konfiguracyjnych. Istnieją także opcjonalne funkcje, w tym pule klientów i zespoły windykacji. 

- Definicje okresów wiekowania
- Migawki wiekowania
- Nazwy arkuszy
- Kod przyczyny odpisania transakcji
- Agenci ds. windykacji
- Konto odpisów
- Informacja o niewystarczających funduszach (NSF)
- Konfigurowanie ustawień programu Outlook dla użytkowników na stronie **Windykacja**
- Adresy e-mail

Te punkty omówiono szczegółowo w dalszej części tego tematu. 

<a name="set-up-aging-period-definitions"></a>Ustaw definicje okresów wiekowania
-------------------------------

Ustaw definicję okresu wiekowania. Definicja okresu wiekowania określa kolumny wyświetlane na stronach listy **Wiekowane salda**, **Działania związane z windykacją** i **Sprawy dotyczące windykacji**. Określa także okresy, które pojawiają się na stronie **Windykacja**. Jeśli pula klientów jest ustawiona, definicja okresu wiekowania dla puli jest używana. Jeśli nie są ustawione żadne pule, używana jest domyślna definicja okresu wiekowania, określona na stronie **Parametry modułu rozrachunków z odbiorcami**. Jeśli nie określono domyślnego okresu wiekowania, używana jest pierwsza definicja okresu wiekowania ze strony **Definicje okresów wiekowania**.

## <a name="create-an-aging-snapshot"></a>Utwórz aktualizację migawki wiekowania
Utwórz migawkę wiekowania dla rekordów dla wszystkich odbiorców lub dla odbiorców w puli klientów. Informacje migawki wiekowania pojawiają się na stronie listy **Wiekowane salda** i na stronie **Windykacja**. Należy utworzyć migawki wiekowania, aby można było używać strony listy. Strona listy pokazuje tylko informacje dla odbiorców, dla których została utworzona migawka wiekowania.

## <a name="optional-set-up-customer-pools"></a>Opcjonalnie: Ustawianie pul odbiorców
Istnieje możliwość skonfigurowania pul klientów, aby reprezentować grupy odbiorców. Można używać pul klientów, takich jak filtry dla informacji o odbiorcy, które są wyświetlane na stronach listy kolekcji na stronach listy **Windykacja** na stronie **Windykacja** lub podczas tworzenia migawki wiekowania.

## <a name="optional-create-a-collections-team"></a>Opcjonalnie: Tworzenie zespołu ds. windykacji
Wiele osób w organizacji wykonuje prace związane z windykacją, więc można skonfigurować zespoły ds. windykacji. Umożliwia wybór zespołu na stronie **Parametry modułu rozrachunków z odbiorcami**. Jeśli nie utworzysz zespołu ds. windykacji, zostanie on utworzony automatycznie podczas konfigurowania agentów ds. windykacji na stronie **Agent ds. windykacji**.

## <a name="set-up-a-collections-case-category"></a>Tworzenie kategorii spraw windykacyjnych
Jeśli uporządkujesz pracę zespołów według spraw, zdefiniuj kategorię z typem kategorii **Windykacja**. Jest to wymagane tylko wtedy, gdy chcesz używać funkcji spraw na stronie **Windykacje**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Umożliwia tworzenie nazw arkuszy (rozliczenie, odpis, niewystarczające fundusze)
Możesz ustawić nazwy arkuszy, które są używane podczas przetwarzania transakcji na stronie **Windykacja**. Ten proces obejmuje rozliczanie transakcji, odpisy transakcji i przetwarzanie płatności przy niewystarczających funduszach (NSF).

| Opis | Typ arkusza     |
|-------------|------------------|
| Miejscowość  | Płatność od odbiorcy |
| Zmniejszenie   | Dziennie            |
| NF         | Płatność od odbiorcy |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Tworzenie kodu przyczyny dla transakcji odpisu
Można skonfigurować domyślny kod przyczyny używany, gdy transakcje są odpisywane na stronie **Windykacja**. Można zmienić kod w procesie odpisu.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Skonfigurowanie folderu dla załączników do wiadomości i tworzenie szablonów wiadomości e-mail
Jeśli wysyłasz wiadomości e-mail ze strony **Windykacja**, na której są załączniki Microsoft Excel, można utworzyć opcjonalne szablony wiadomości e-mail dla tych wiadomości.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Ustawianie parametrów windykacji Rozrachunki z odbiorcami
Można ustawić parametry modułu Rozrachunki z odbiorcami, które są widoczne na karcie **Windykacja**.

## <a name="optional-set-up-collections-agents"></a>Opcjonalnie: Ustawianie agentów ds. windykacji
Wiele osób w organizacji wykonuje czynności windykacyjne, więc można skonfigurować agentów ds. windykacji. Agent ds. windykacji jest pracownikiem, który jest skonfigurowany jako użytkownik na stronie **Relacje użytkownika**. Można przypisać pule in klientów agentów ds. windykacji, co pomaga organizowania ich pracę. Agenci ds. windykacji są dodawani do zespołu wybranego na stronie **Parametry rozrachunków z odbiorcami**. Jeśli zespół nie został wybrany na tej stronie, nowy zespół o nazwie **Windykacja** jest tworzony automatycznie, a agenci ds. windykacji są dodawanie do tego zespołu.

## <a name="set-up-a-writeoff-account"></a>Konfigurowanie konta odpisów
Można utworzyć konto odpisu, które będzie używane dla odpisów z księgi głównej przy odpisach transakcji. To konto jest przechowywane w profilu księgowania odbiorcy.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Konfigurowanie informacji NSF dla kont bankowych
Można zaktualizować konta bankowe, tak by miały prawidłowy arkusz w chwili identyfikacji płatności przy niewystarczających funduszach na stronie **Windykacja**. Na karcie **Zarządzanie walutami** w polu **Arkusz płatności przy niewystarczających funduszach** wybierz arkusz płatności.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Konfigurowanie ustawień programu Outlook dla użytkowników na stronie Windykacja
Aby umożliwić pracownikom tworzenie działań lub wysyłanie e-maili za pomocą strony **Windykacja**, musisz zweryfikować, czy wybrany jest klucz konfiguracji **synchronizacji z programem Microsoft Outlook** i czy dla tych pracowników ustawiona jest synchronizacja z programem Outlook.

## <a name="set-up-email-and-addresses"></a>Konfigurowanie wiadomości e-mail i adresów
Za pomocą poczty e-mail można komunikować się zarówno z klientami, jak i sprzedawcami w sprawie problemów z windykacjami w celu wysyłania wiadomości e-mail ze strony **windykacji**. 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Konfigurowanie ustawień wysyłania wiadomości e-mail do osób kontaktowych ds. windykacji odbiorców
Można ustawić adresy e-mail dla kontaktów odbiorcy, by wysyłać wiadomości e-mail do tych kontaktów ze strony **Windykacja**. Osoba kontaktowa ds. windykacji jest domyślną osobą kontaktową na stronie **Windykacja**. Można skonfigurować adres zestawienia dla odbiorcy, jeśli zestawienia mają mieć adres inny niż adres podstawowy. 

Na skróconej karcie **Kredyty i windykacja** dla odbiorcy, w polu **Osoba kontaktowa ds. windykacji** wybierz osoby w organizacji odbiorcy, która współpracuje z Twoim agentem ds. windykacji. Ta osoba jest używana jako domyślna osoba kontaktowa na stronie **Windykacje** i do tej osoby wysyłane są e-maile. 

> [!NOTE] 
> Jeśli nie określono dla odbiorcy osoby kontaktowej ds. windykacji, używany jest kontakt podstawowy. Jeśli kontakt podstawowy nie jest określony, wiadomości e-mail wysyłane są na pierwszy adres wymieniony na stronie **Kontakty**.

### <a name="set-up-email-settings-for-salespeople"></a>Konfigurowanie ustawień wiadomości e-mail dla sprzedawców
Ustaw adresy e-mail dla sprzedawców, by wysyłać wiadomości e-mail do sprzedawców ze strony **Windykacja**. Ustaw adres e-mail dla każdego przedstawiciela handlowego w każdej grupie prowizji sprzedaży. Przedstawiciel handlowy, który ma zaznaczoną opcję **Kontakt**, jest domyślnym sprzedawcą, do którego są wysyłane wiadomości e-mail. 

Jeśli przedstawiciel handlowy nie jest określony, podstawowy sprzedawca dla organizacji używa odbiorcy. Jeśli sprzedawca podstawowy nie jest określony, wiadomości e-mail wysyłane są na pierwszy adres z listy sprzedawców wymieniony na stronie.


Aby uzyskać więcej informacji, zobacz następujące tematy:

 - [Tworzenie kolejności ponagleń](tasks/create-collection-letter-sequence.md)

 - [Przetwarzanie ponagleń](tasks/process-collection-letters.md)

 - [Przeglądanie informacji o windykacji](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
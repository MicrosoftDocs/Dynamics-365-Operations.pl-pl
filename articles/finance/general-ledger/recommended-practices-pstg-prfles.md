---
title: Zalecane wskazówki dotyczące profili księgowania
description: W tym temacie opisano zalecane wskazówki dotyczące konfigurowania profilów księgowania.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 211dc42b80089eb1f59a435f09d6e9d9f956736b
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734283"
---
# <a name="recommended-practices-for-posting-profiles"></a>Zalecane wskazówki dotyczące profili księgowania

Podczas konfigurowania profilów księgowania w systemie należy postępować zgodnie z kilkoma zalecanymi praktykami. W tym temacie opisano różne scenariusze i odpowiednie zalecane rozwiązania.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Ustawianie flagi Nie zezwalaj na wprowadzanie ręczne

Na stronie **Konta główne** pole wyboru **Nie zezwalaj na wprowadzanie ręczne** powinno być zaznaczone dla każdego konta głównego używanego dla profilu księgowania. To ustawienie uniemożliwia użytkownikom ręczne księgowanie zapisu arkusza na koncie głównym. Dzięki temu pomaga zapewnić, że księga podrzędna pozostaje w bilansie z księgą główną i ułatwia proces uzgadniania.

Jeśli są wymagane korekty konta kontrolowanego przez system i automatycznie księgowane, można użyć jednego z tych podejść:

- Umożliwia tworzenie pomocniczego konta głównego, na którym można księgować korekty. Następnie użyj konta sum lub specjalnego wiersza w raportach finansowych, aby zgrupować i zsumować konta.
- Wycofaj oryginalne transakcje w odpowiednim poddarze, dokonaj wymaganych korekt, a następnie zaksięguj transakcję ponownie za pomocą tego samego dokumentu podrzędnego.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Zmiana profilów księgowania po istniejących transakcjach

Jeśli profil księgowania zostanie zmieniony po istniejących transakcjach, uzgodnienie może się nie powieść, a księga podrzędna i księga mogą stać się zbilansowane. Ogólnie zaleca się, aby po istniejących transakcjach **nie** zmieniać profilu księgowania.

Jeśli są wymagane zmiany, aby zapewnić integralność systemu, należy skorzystać z następujących wskazówek:

- Zmiany należy wprowadzać podczas zamykania okresu.
- Wprowadzaj zmiany, jeśli w systemie nie ma innych transakcji.
- Sprawdź poprawność księgi i uzgodnij ją z księgą podrzędną przed i po wy wywłasz dopiero po wywłaceniu zmian.
- Jeśli zmienisz profil księgowania, zaksięgowane transakcje nie zostaną zaktualizowane. Rozważ, czy każda korekta wpisów jest wymagana dla zmiany.
- Podczas zmieniania profilów księgowania zapasów należy wziąć pod uwagę wpływ zmian na stan zapasów i salda księgi. Niektóre zmiany mogą wymagać zawęzienia zapasów do wartości 0 (zero), zamknięcia magazynu, a następnie przywrócenia zapasów po ich wywróceniu.
- Zawsze testuj zmiany w środowisku nieprodukcyjnym przed ich rozpoczęciem w produkcji.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Rejestrowanie bazy danych w celu inspekcji zmian profilów księgowania

Rozważ skonfigurowanie rejestrowania bazy danych dla każdego profilu księgowania i tabel parametrów, które sterują księgowaniu. Następnie w przypadku zmiany parametru lub profilu użytkownik będzie mieć pełny rekord inspekcji, który z nich uległ zmianie, kto ją zmienił, kiedy i co była poprzednią wartością. Te informacje mogą mieć krytyczne znaczenie w procesie uzgadniania, a audytor może wymagać dokumentacji dodatkowej.

Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie rejestrowaniem bazy danych](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Poniższej tabeli należy użyć jako odwołania do wspólnych nazw tabel powiązanych z profilami księgowania i powiązanymi parametrami księgowania.

| Nazwa strony | Ścieżka nawigacji | Nazwa tabeli |
|-----------|-----------------|------------|
| Parametry modułu rozrachunków z dostawcami | Rozrachunki z dostawcami &gt; Ustawienia &gt; Parametry modułu rozrachunków z dostawcami | VendParm |
| Profil księgowania dostawcy | Wybierz kolejno opcje Rozrachunki z dostawcami &gt; Ustawienia &gt; Profil księgowania dostawców. | VendPosting |
| Kod opłat | Rozrachunki z dostawcami &gt; Konfiguracja opłat &gt; Kod opłat lub Rozrachunki z odbiorcami &gt; Konfiguracja opłat &gt; Kod opłat | MarkupTable |
| Metody płatności | Rozrachunki z dostawcami &gt; Ustawienia płatności &gt; Metody płatności | VendPaymMode |
| Rabaty gotówkowe | Rozrachunki z dostawcami &gt; Konfiguracja płatności &gt; Rabaty gotówkowe lub Rozrachunki z odbiorcami &gt; Konfiguracja płatności &gt; Rabaty gotówkowe | CashDisc |
| Opłata za płatność (dostawca) | Rozrachunki z dostawcami &gt; Ustawienia płatności &gt; Opłata | VendPaymFee |
| Parametry modułu rozrachunków z odbiorcami | Rozrachunki z dostawcami &gt; Ustawienia &gt; Parametry modułu rozrachunków z odbiorcami | CustParm |
| Profile księgowania odbiorców | Rozrachunki z odbiorcami &gt; Ustawienia &gt; Profil księgowania odbiorców | CustPosting |
| Metody płatności | Rozrachunki z odbiorcami &gt; Ustawienia płatności &gt; Metody płatności | CustPaymMode |
| Opłata za płatność (Klient) | Rozrachunki z odbiorcami &gt; Ustawienia płatności &gt; Metody płatności | CustPaymFee |
| Parametry wynajmu składnika majątku | Wynajem składnika majątku &gt; Ustawienia &gt; Parametry wynajmu składników majątku | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Konta bankowe | Zarządzanie gotówką i bankami &gt; Konta bankowe &gt; Konta bankowe | BankAccountsTable |
| Typy transakcji bankowych | Zarządzanie gotówką i bankami &gt; Ustawienia &gt; Rodzaje transakcji bankowych | BankTransType |
| Reguły eliminacji | Konsolidacje &gt; Ustawienia &gt; Reguła eliminacji | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Kategorie wydatków | Zarządzanie wydatkami &gt; Ustawienia &gt; Ogólne &gt; Kategorie wydatków | ProjCategories |
| Parametry środków trwałych | Środki trwałe &gt; Ustawienia &gt; Parametry środków trwałych | AssetParameters |
| Profile księgowania środków trwałych | Środki trwałe &gt; Ustawienia &gt; Profile księgowania środków trwałych | AssetLedgerAccounts<br>AssetDisposalParameters |
| Konta przeszacowania waluty | Księga główna &gt; Waluty &gt; Konta przeszacowania waluty | CurrencyLedgerGainLossAccount |
| Konta dla transakcji automatycznych | Księga główna &gt; Ustawienia księgowania &gt; Konta dla transakcji automatycznych | LedgerSystemAccounts |
| Księgowanie międzyfirmowe | Księga główna &gt; Ustawienia księgowania &gt; Księgowanie międzyfirmowe | LedgerIntercompany |
| Definicje księgowania transakcji | Księga główna &gt; Ustawienia księgowania &gt; Definicje księgowania transakcji | JournalizingDefinitionTrans |
| Definicje księgowania | Księga główna &gt; Ustawienia księgowania &gt; Definicje księgowania | JournalizingDefintion |
| Księgowanie (zapasy) | Zarządzanie zapasami &gt; Konfiguracja &gt; Księgowanie &gt; Księgowanie | InventPosting |
| Kody typów kosztu | Koszt z wyładunkiem &gt; Konfiguracja wyceny &gt; Kody typów kosztu | ITMCostTypeTable |
| Zasoby | Kontrola produkcji &gt; Ustawienia &gt; Zasoby &gt; Zasoby | WrkCtrTable |
| Grupy zasobów | Kontrola produkcji &gt; Ustawienia &gt; Zasoby &gt; Grupy zasobów | WrkCtrResourceGroup |
| Grupy produkcji | Kontrola produkcji &gt; Ustawienia &gt; Produkcja &gt; Grupa produkcji | ProdGroup |
| Kategorie kosztu | Kontrola produkcji &gt; Konfiguracja &gt; Marszruty &gt; Kategorie kosztu | Kategoria projektu |
| Grupy projektów | Zarządzanie projektami i ich księgowanie &gt; Konfiguracja &gt; Księgowanie &gt; Grupy projektów | ProjGroup |
| Konfiguracja księgowania (projekty) | Zarządzanie projektami i ich księgowanie &gt; Ustawienia &gt; Księgowanie &gt; Konfiguracja księgowania | ProjPosting |
| Domyślne konta przeciwstawne dla wydatków | Zarządzanie projektami i ich księgowanie &gt; Konfiguracja &gt; Księgowanie &gt; Domyślne konta przeciwstawne dla wydatków | ProjDefaultOffsetSetup |
| Profile publikowania zarządzania rabatami | Zarządzanie rabatami &gt; Konfiguracja księgowania dla modułu Zarządzanie rabatami &gt; Profile księgowania zarządzania rabatami | TAMRebatePosting |
| Grupa księgowania (podatek) | Podatek &gt; Ustawienia &gt; Podatek &gt; Grupy księgowania | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Zmiana grup po istniejących transakcjach

W przypadku zmiany grup w danych głównym należy zachować ostrożność. Jeśli do definiowania profilów księgowania są używać grup, każda zmiana grupy w rekordzie głównym może mieć negatywny wpływ na możliwość uzgadniania księgi z księgą podrzędną. Na przykład można skonfigurować profil księgowania zapasów dla przychodów z zamówienia sprzedaży, aby dla każdej grupy towarów było używane inne konto przychodów. Jeśli zmienisz grupę towarów przypisaną do towaru po istniejących transakcjach, przychody z nowych transakcji zostaną zaksięgowane na zaktualizowanym koncie. Jednak każdy przychód zaksięgowany przed zmianą pozostanie na oryginalnym koncie.

## <a name="testing-posting-profiles"></a>Testowanie profili księgowania

Przed rozpoczęciem pracy oraz po wyległych profilach księgowania lub innych pokrewnych parametrach należy przetestować każdy scenariusz. Należy co najmniej przetestować każdy typ księgowania, aby sprawdzić, czy księgowanie działa poprawnie. Jednak zalecane jest przetestowanie każdej transakcji i kombinacji profilu księgowania.

Na przykład istnieją dwa profile księgowania odbiorcy, z których każdy ma trzy rekordy specyficzne dla grup klientów. W takim przypadku należy przetestować każdy typ transakcji.

**Profile księgowania:**

- **GEN** — ogólny profil księgowania, który ma jedną grupę dla pracowników, jedną dla odbiorców i jedną dla międzyfirmowych. Każda grupa wskazuje inne konto handlowe rozrachunków z odbiorcami.
- **PRE** – profil księgowania przedpłat z jednym rekordem dla wszystkich przedpłat oznaczających konta przedpłaty odbiorcy.

### <a name="testing-scenarios"></a>Testowanie scenariuszy

- Faktura free text dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **GEN**
- Faktura free text dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **PRE**
- Faktura zamówienia sprzedaży dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **GEN**
- Faktura zamówienia sprzedaży dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **PRE**
- Arkusz płatności odbiorcy dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **GEN**
- Arkusz płatności odbiorcy dla odbiorcy z grupy **Pracownicy**, który korzysta z profilu księgowania **PRE**

W poprzednim przykładzie powtórz jeden scenariusz testowania dla każdej grupy klientów i powtórz każdą grupę scenariuszy testowania dla każdego dodatkowego typu transakcji (na przykład faktury projektu i zarządzanie serwisem).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Pogodzenie księgi z księgą pomocniczą

Księga powinna być uzgadniana z księgą podrzędną w każdym okresie. Wiele modułów zawiera raporty out of box, które mogą być używane do tego uzgodnienia. Jednak w zależności od wymagań lokalnych może być konieczne opracowywanie raportów niestandardowych lub rozszerzanie istniejących raportów w celu spełnienia wymagań dotyczących raportowania.

Zaleca się, aby przed rozpoczęciem sprzedaży uzgodnić każdą księgę podrzędną w księdze. Ponadto przed początkowym rozpoczęciem pracy zaleca się odjęcie odejmowania wszystkich otwartych sald i otwartych transakcji. W ramach tego procesu należy uruchomić pełne uzgadnianie, aby zagwarantować, że migracja sald i otwartych transakcji będzie zbilansowana ze starszego systemu oraz że wszystkie księgi podrzędne będą bilansowane z księgą przed ich utworzeniem.

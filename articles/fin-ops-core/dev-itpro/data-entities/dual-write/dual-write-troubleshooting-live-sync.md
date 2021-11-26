---
title: Rozwiązywanie problemów z synchronizacją na żywo
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 69667f8b64c048f5957168d1af21a6c858bc0bad
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782586"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Rozwiązywanie problemów z synchronizacją na żywo

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Microsoft Dataverse. Ten temat zawiera informacje, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Azure Active Directory (Azure AD). W każdej sekcji wyjaśniono, czy określona rola lub określone poświadczenia są wymagane.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>Synchronizacja na żywo pokazuje błąd podczas tworzenia wiersza

Może pojawić się następujący komunikat o błędzie podczas tworzenia wiersza w aplikacji Finance and Operations:

*\[{\\„błąd\\”:{\\„kod\\”:\\„0x 80072560\\”,\\„komunikat\\”:\\„użytkownik nie jest członkiem organizacji.\\”}}\], Serwer zdalny zwrócił błąd: (403) zabroniony”}}”.*

Aby rozwiązać ten problem, należy wykonać kroki opisane w [Wymagania systemowe i wymagania wstępne](requirements-and-prerequisites.md). Aby wykonać te kroki, użytkownicy aplikacji podwójnego odpisu, którzy utworzyli w Dataverse, muszą mieć rolę administratora systemu. Domyślny zespół będący właścicielem musi mieć również rolę Administratora systemu.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>Synchronizacja na żywo pokazuje błąd podczas próby zapisania danych tabeli

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Może pojawić się następujący komunikat o błędzie podczas próby zapisania danych tabeli w aplikacji Finance and Operations:

*Nie można zapisać zmian w bazie danych. Jednostka pracy nie może zatwierdzić transakcji. Nie można zapisać danych do jednostki uoms. Zapis do UnitOfMeasureEntity nie powiódł się. Komunikatu o błędzie nie można zsynchronizować z jednostką uoms.*

Aby rozwiązać ten problem, upewnij się, że istnieją dane referencyjne wymagań wstępnych w aplikacji Finance and Operations i Dataverse. Jeśli na przykład rekord klienta należy do konkretnej grupy klientów, należy upewnić się, że rekord grupy klientów istnieje w usłudze Dataverse.

Jeśli istnieją dane w obu miejscach i potwierdzono, że ten błąd nie jest związany z danymi, wykonaj następujące kroki.

1. Otwórz encję **DualWriteProjectConfigurationEntity** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku programu Excel Finance and Operations i dodaj do arkusza encję **DualWriteProjectConfigurationEntity**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
2. Wybierz i usuń rekordy, które mają problemy w mapie i projekcie podwójnego zapisu. Dla każdego mapowania podwójnego zapisu będą dostępne dwa rekordy.
3. Opublikuj zmiany przy użyciu dodatku programu Excel. Ten krok jest ważny, ponieważ powoduje usunięcie rekordów z encji i tabel źródłowych.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Obsługa błędów uprawnień do odczytu lub odczytu podczas tworzenia danych w aplikacji Finance and Operations

Może pojawić się komunikat o błędzie „Nieprawidłowe żądanie” podczas tworzenia danych w aplikacji Finance and Operations.

![Przykład komunikatu o błędzie złego żądania.](media/error_record_id_source.png)

Aby rozwiązać ten problem, należy włączyć brakujące uprawnienie, przypisując poprawną rolę zabezpieczeń zespołowi zamapowanej jednostki biznesowej usługi Dynamics 365 Customer Service lub Dynamics 365 Sales.

1. W aplikacji Finance and Operations znajdź jednostkę biznesową, która jest zamapowana w zestawie połączenia integracji danych.

    ![Mapowanie organizacji.](media/mapped_business_unit.png)

2. W aplikacji angażującej klienta zaloguj się do środowiska, przejdź do pozycji **Ustawienia \> Zabezpieczenia** i znajdź zespół zamapowanej jednostki biznesowej.

    ![Zespół zamapowanej jednostki biznesowej.](media/setting_security_page.png)

3. Otwórz stronę zespołu do edycji, a następnie wybierz pozycję **Zarządzaj rolami**.

    ![Przycisk Zarządzaj rolami.](media/manage_team_roles.png)

4. W oknie dialogowym **Zarządzanie rolami zespołu** przypisz rolę, która ma uprawnienie do odczytu/zapisu dla odpowiednich tabel, a następnie wybierz przycisk **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Poprawianie problemów z synchronizacją w środowisku, w którym jest ostatnio zmienione środowisko Dataverse

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Może pojawić się następujący komunikat o błędzie podczas tworzenia danych w aplikacji Finance and Operations:

*{„EntityName”: „CustCustomerV3Entity”, „executionStatus”: 2, „fieldResponses”:\[\], „recordResponses”:\[{„ErrorMessage”: „**nie można wygenerować ładunku dla jednostki CustCustomerV3Entity**”, „logDateTime”: „2019-08-27T 18:51:52.5843124Z”, „verboseError”: „Tworzenie ładunku nie powiodło się z powodu błędu nieprawidłowy identyfikator URI: identyfikator URI jest pusty”}\], „isErrorCountUpdated”: prawda}*

Oto jak wygląda komunikat o błędzie w aplikacji angażującej klienta:

> Wystąpił nieoczekiwany błąd w kodzie ISV. (Błąd = ClientError) Nieoczekiwany wyjątek od wtyczki (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nie można przetworzyć konta jednostki — (Próba połączenia nie powiodła się, ponieważ połączona strona nie odpowiedziała prawidłowo po upływie określonego czasu lub ustanowienie połączenia nie powiodło się, ponieważ połączony host nie odpowiedział.

Ten błąd występuje, gdy środowisko Dataverse jest niepoprawnie resetowane podczas próby utworzenia danych w aplikacji Finance and Operations.

> [!IMPORTANT]
> Jeśli środowiska zostały ponownie połączone, musisz zatrzymać wszystkie mapy encji przed kontynuowaniem kroków ograniczenia ryzyka.

Aby rozwiązać ten problem, musisz wykonać kroki w usłudze Dataverse i aplikacji Finance and Operations.

1. W aplikacji Finance and Operations wykonaj następujące kroki:

    1. Otwórz encję **DualWriteProjectConfigurationEntity** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku programu Excel Finance and Operations i dodaj do arkusza encję **DualWriteProjectConfigurationEntity**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
    2. Wybierz i usuń rekordy, które mają problemy w mapie i projekcie podwójnego zapisu. Dla każdego mapowania podwójnego zapisu będą dostępne dwa rekordy.
    3. Opublikuj zmiany przy użyciu dodatku programu Excel. Ten krok jest ważny, ponieważ powoduje usunięcie rekordów z encji i tabel źródłowych.
    4. Aby zapobiec błędom po ponownym połączeniu środowisk Finance and Operations lub Dataverse, należy upewnić się, że nie pozostają żadne konfiguracje podwójnego zapisu.

2. W usłudze Dataverse wykonaj następujące kroki:

    1. Zaloguj się do środowiska usługi Dataverse (na przykład `https://*****.crm.dynamics.com/`).
    2. Przejdź do pozycji **Ustawienia zaawansowane** \> **Wyszukiwanie zaawansowane**.
    3. Wybierz pozycję **Konfiguracja środowiska uruchomieniowego podwójnego zapisu**.
    4. Zaznacz kolumnę, którą chcesz wyświetlić.
    5. Wybierz opcję **Wyniki**, aby wyświetlić konfiguracje.
    6. Usuń wszystkie wystąpienia.

3. W aplikacji Finance and Operations wykonaj następujące kroki:

    1. Otwórz encję **DualWriteProjectConfigurationEntity** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku programu Excel Finance and Operations i dodaj do arkusza encję **DualWriteProjectConfigurationEntity**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
    2. Wybierz i usuń rekordy, które mają problemy w mapie i projekcie podwójnego zapisu. Dla każdego mapowania podwójnego zapisu będą dostępne dwa rekordy.
    3. Opublikuj zmiany przy użyciu dodatku programu Excel. Ten krok jest ważny, ponieważ powoduje usunięcie rekordów z encji i tabel źródłowych.
    4. Aby zapobiec błędom po ponownym połączeniu środowisk Finance and Operations lub Dataverse, należy upewnić się, że nie pozostają żadne konfiguracje podwójnego zapisu.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Błąd synchronizacji na żywo po zakończeniu wykonywania pełnej kopii bazy danych

Po uruchomieniu pełnej kopii bazy danych z jednego systemu do drugiego i próbie uruchomienia operacji na bazie danych może zostać wyświetlony następujący komunikat o błędzie:

*Organizacja SecureConfig (???) nie pasuje do rzeczywistej organizacji CRM (???).*

Komunikat o błędzie jest wyświetlany z dodatku środowiska uruchomieniowego podwójnego zapisu, co zapewnia, że konfiguracja podwójnego zapisu ustawiona w jednym systemie nie może być używana w innym systemie.

Aby rozwiązać ten problem, po przywróceniu bazy danych usuń wszystkie rekordy z tabeli **msdyn_dualwriteruntimeconfig**. Aby uzyskać więcej informacji, zobacz temat [Odłączanie i ponownie podłączanie środowiska podwójnego zapisu](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problemy z synchronizacją na żywo spowodowane przez niepoprawną składnię filtra zapisu na mapach podwójnego zapisu

Nawet jeśli wyrażenie zapytania dla filtru map podwójnego zapisu ma poprawną składnię, może nie działać zgodnie z oczekiwaniami. Wyrażenie filtru znajduje się w encji, a nie w jednym źródle danych obiektu zapytania. W związku z tym wygenerowane zapytanie SQL nie zwraca oczekiwanych wyników.

Oto przykład.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Można spodziewać się odfiltrowania projektów bez elementu nadrzędnego. Jednak filtr nie działa, ponieważ jest tłumaczony na zapytanie przypominające poniższy przykład.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

W wyniku tego pole `parentProject` jest szacowane jako `null`. Jednak ciąg `null` nie jest taki sam jak ciąg pusty. Z powodu tej niezgodności filtr zapytania nie zwraca prawidłowych wyników.

Aby naprawić problem, należy wykonać następujące czynności.

1. Dodaj kolumnę obliczaną, która może zostać dodana do modelu rozszerzenia i która jest wspierana przez logikę konwertującą wartość `null` na pusty ciąg.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Użyj filtru w nowej kolumnie obliczanej zamiast domyślnej kolumny.

Aby ocenić filtr w środowisku programowania, można użyć następującego kodu X++, aby zweryfikować wyniki. Uruchom ten kod jako program autonomiczny. Przed użyciem tych filtrów na mapach podwójnego zapisu można go używać do szacowania różnych rodzajów filtrów, które są odpowiednie dla encji. Zapytanie można uruchomić na bazie danych w celu oszacowania niezgodności.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Dane z aplikacji Finance and Operations nie są synchronizowane z usługą Dataverse

Podczas synchronizacji na żywo może wystąpić problem, gdy tylko część danych jest synchronizowana z aplikacji Finance and Operations do usługi Dataverse lub dane w ogóle nie są synchronizowane.

> [!NOTE]
> Ten problem należy rozwiązać podczas developmentu.

Przed rozpoczęciem rozwiązania problemu przejrzyj następujące wymagania wstępne:

+ Upewnij się, że niestandardowe zmiany zostały zapisane w zakresie jednej transakcji.
+ Zdarzenia biznesowe i struktura podwójnego zapisu nie obsługują operacji `doinsert()`, `doUpdate()` ani `recordset()` lub rekordów z oznaczonym elementem `skipBusinessEvents(true)`. Jeśli kod znajduje się wewnątrz tych funkcji, podwójny zapis nie będzie wyzwalany.
+ Zdarzenia biznesowe muszą być zarejestrowane dla źródła danych, które jest mapowane. Niektóre źródła danych mogą używać sprzężenia zewnętrznego i mogą być oznaczone jako tylko do odczytu w aplikacjach Finance and Operations. Te źródła danych nie są śledzone.
+ Zmiany będą wyzwalane tylko wtedy, gdy modyfikacje są w mapowanych polach. Niezamapowane modyfikacje pól nie będą wyzwalać podwójnego zapisu.
+ Upewnij się, że oceny filtru zapewniają prawidłowy wynik.

### <a name="troubleshooting-steps"></a>Kroki rozwiązywania problemów

1. Przejrzyj mapowania pól na stronie administrowania podwójnym zapisem. Jeśli pole nie jest mapowane z aplikacji Finance and Operations do usługi Dataverse, nie będzie śledzone. Na przykład na poniższej ilustracji pole **Opis** jest śledzone z usługi Dataverse, ale nie z aplikacji Finance and Operations. Zmiany tego pola w aplikacjach Finance and Operations nie będą śledzone.

    ![Śledzone pole.](media/live-sync-troubleshooting-1.png)

2. Określ, czy źródło danych jest śledzone w definicji zdarzeń biznesowych. Na przykład na poniższej ilustracji zmiany nie będą śledzone w polach tabeli **DefaultDimensionDAVs** i tabel źródłowych. Źródła danych, które korzystają z sprzężenia zewnętrznego i które są oznaczone jako tylko do odczytu, nie są śledzone.

    ![Pole, które nie jest śledzone.](media/live-sync-troubleshooting-2.png)

3. Określ, czy zamapowane pola tabeli mają być wyświetlane w tabeli **BUSINESSEVENTSDEFINITION**, jak pokazano na poniższej ilustracji. Jeśli nie znajdziesz pola, którego szukasz w wyniku zapytania, nie zostanie ono wywołane przez podwójny zapis.

    ![Śledzone pole w tabeli.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Przykładowy scenariusz

W aplikacjach Finance and Operations istnieje aktualizacja adres rekordu kontaktu, ale zmiana adresu nie jest synchronizowana z usługą Dataverse. Ten scenariusz występuje, ponieważ żaden rekord w tabeli **BusinessEventsDefinition** nie zawiera kombinacji tej tabeli i encji. W szczególności tabela **LogisticsPostalAddress** nie jest bezpośrednim źródłem danych dla encji **smmContactpersonCDSV2Entity**. Źródłem danych encji **smmContactpersonCDSV2Entity** jest encja **smmContactPersonV2Entity**, a z kolei źródłem danych encji **smmContactPersonV2Entity** jest encja **LogisticsPostalAddressBaseEntity**. Tabela **LogisticsPostalAddress** jest źródłem danych dla encji **logisticsPostalAddressBaseEntity**.

Podobna sytuacja może wystąpić w pewnych niestandardowych wzorcach, takich jak przypadki, w których tabela modyfikowana w aplikacjach Finance and Operations nie jest w oczywisty sposób połączona z zawierającą ją encją. Na przykład dane adresu podstawowego są obliczane w encji **smmContactPersonCDSV2Entity**. Struktura podwójnego zapisu próbuje ustalić, w jaki sposób zmiana w tabeli podstawowej jest mapowana z powrotem na encje. Zwykle to podejście jest wystarczające. Jednak w niektórych przypadkach połączenie jest tak złożone, że należy je dokładnie zdefiniować. Musisz się upewnić, że identyfikator powiązanej tabeli **RecId** jest bezpośrednio dostępny w encji. Następnie dodaj statyczną metodę w celu monitorowania tabeli pod kątem zmian.

Aby zapoznać się z przykładem, zapoznaj się z metodą **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. Encje **CustCustomerV3entity** i **VendVendorV2Entity** zostały zmodyfikowane, aby obsłużyć tę sytuację.

Aby naprawić problem, należy wykonać następujące czynności.

1. Dodaj pole **PrimaryPostalAddressRecId** do encji **smmContactPersonV2Entity**. Oznacz je jako wewnętrzne.

    ![Pole dodane do encji smmContactPersonV2Entity.](media/Troubleshoot_live_sync_issue_1.png)

2. Dodaj identyczne pole do encji **smmContactPersonCDSV2Entity**.

    ![Pole dodane do encji smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Dodaj następującą metodę do klasy **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Zsynchronizuj bazę danych i skompiluj aplikację.
5. Zatrzymaj wszystkie mapy podwójnego zapisu utworzone w encji **smmContactPersonCDSV2Entity**.
6. Uruchom mapę. Powinna pojawić się nowa tabela (**LogisticsPostalAddress** w tym przykładzie), która była śledzona za pomocą kolumny **RefTableName** dla wiersza, w którym wartość **refentityname** jest równa **smmContactPersonCDSV2Entity** w tabeli **BusinessEventsDefinition**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Błąd podczas tworzenia rekordu, w którym wiele rekordów jest wysyłanych z aplikacji Finance and Operations do usługi Dataverse w tej samej partii

W przypadku każdej transakcji aplikacja Finance and Operations tworzy dane w partii i wysyła je jako partię do usługi Dataverse. Jeśli w ramach tej samej transakcji utworzone zostaną dwa rekordy i odwołują się one do siebie, może zostać wyświetlony komunikat o błędzie przypominający następujący przykład w aplikacji Finance and Operations:

*Nie można zapisać danych do encji aaa_fundingsources. Nie można odszukać danych ebecsfs_contracts z wartościami {PC00...}. Nie można odszukać danych aaa_fundingsources z wartościami {PC00...}. Zapisy w aaa_fundingsources nie powiodły się; komunikat o błędzie: Sserwer zdalny zwrócił błąd: (400) Nieprawidłowe żądanie.*

Aby rozwiązać ten problem, utwórz w aplikacji Finance and Operations relacje encji, aby wskazać, że te dwie encje są ze sobą powiązane oraz że powiązane rekordy są obsługiwane w tej samej transakcji.

## <a name="enable-verbose-logging-of-error-messages"></a>Włącz pełne rejestrowanie komunikatów o błędach

W aplikacji Finance and Operations mogą wystąpić błędy związane ze środowiskiem usługi Dataverse. Komunikat o błędzie może nie zawierać pełnego tekstu wiadomości lub innych odpowiednich danych. Aby uzyskać więcej informacji, można włączyć pełne rejestrowanie, ustawiając flagę **IsDebugMode** dostępną w encji **DualWriteProjectConfigurationEntity** we wszystkich konfiguracjach projektów w aplikacjach Finance and Operations.

1. Otwórz encję **DualWriteProjectConfigurationEntity** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku programu Excel Finance and Operations i dodaj do arkusza encję **DualWriteProjectConfigurationEntity**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
2. Ustaw flagę **IsDebugMode** na **Tak** dla projektu.
3. Uruchom scenariusz.
4. Pełne dzienniki są dostępne w tabeli **DualWriteErrorLog**. Aby szukać danych za pomocą przeglądarki tabel, użyj następującego adresu URL: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Aby przechwycić więcej dzienników w trybie debugowania, zainstaluj aktualizację w [KB 4595434 (Poprawka dla wartości pustych wypełnianych w trakcie synchronizacji podwójnego zapisu na żywo)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Błąd podczas dodawania adresu klienta lub kontaktu

Podczas próby dodania adresu klienta lub kontaktu w aplikacjach Finance and Operations lub usłudze Dataverse może pojawić się następujący komunikat o błędzie:

*Nie można zapisać danych do encji msdyn_partypostaladdresses. Zapisy w encji DirPartyPostalAddressLocationCDSEntity nie powiodły się; komunikat o błędzie: Żądanie komunikatu o błędzie nie powiodło się. Kod stanu: BadRequest i kod błędu CDS: 0x80040265, odpowiedź — komunikat: Wystąpił błąd w dodatku plug-in. Rekord z wartościami atrybutów Identyfikator lokalizacji już istnieje. Klucz identyfikatora lokalizacji klucza encji wymaga, aby ten zestaw atrybutów zawierał unikatowe wartości. Wybierz unikatowe wartości i spróbuj ponownie.*

Aby rozwiązać ten problem, zainstaluj pakiet aranżacji podwójnego zapisu w odpowiedniej wersji (2.2.2.60), tak aby klucze w tabeli **Adres** zostały zdefiniowane zgodnie z następującą tabelą.

| Właściwość | Wartość |
|---|---|
| Nazwa wyświetlana | **Klucz lokalizacji** |
| Imię i nazwisko | **msdyn_locationkey** |
| Pola | **msdyn_locationid**, **parentid** |
| Stan | **Aktywni** |
| Zadanie systemowe | Pusty |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Błąd podczas dodawania klienta do usługi Dataverse

Może pojawić się następujący komunikat o błędzie podczas próby dodania klienta w usłudze Dataverse:

*„RecordError0”:„Zapis nie powiódł się dla encji Klienci (wersja 3) z nieznanym wyjątkiem — nie znaleziono rekordu jednostki dla typu strony „Organizacja”}.*

Po utworzeniu klienta w usłudze Dataverse jest generowany nowy numer strony. Komunikat o błędzie jest wyświetlany, gdy rekord klienta oraz strona są synchronizowane z aplikacjami Finance and Operations, ale istnieje już rekord klienta o innym numerze strony.

Aby rozwiązać ten problem, znajdź klienta za pomocą wyszukiwania strony. Jeśli klient nie istnieje, utwórz nowy rekord klienta. Jeśli klient nie istnieje, użyj istniejącej strony, aby utworzyć nowy rekord klienta.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Błąd podczas tworzenia nowego klienta, dostawcy lub kontaktu w usłudze Dataverse

Podczas próby dodania nowego klienta, dostawcy lub kontaktu w usłudze Dataverse może pojawić się następujący komunikat o błędzie:

*Nie można zaktualizować typu strony z „DirOrganization” na „DirPerson”. W zamian należy usunąć istniejącą stronę, a następnie wstawić ją z nowym typem.*

W usłudze Dataverse istnieje sekwencja numerów tabeli **msdyn_party**. Podczas tworzenia konta w usłudze Dataverse jest tworzona nowa strona (na przykład **Strona-001** typu **Organizacja**). Te dane są wysyłane do aplikacji Finance and Operations. Jeśli środowisko Dataverse zostanie zresetowane lub środowisko Finance and Operations zostanie połączone z innym środowiskiem Dataverse, a następnie zostanie utworzony nowy rekord osoby kontaktowej w usłudze Dataverse, zostanie utworzona nowa wartość strony, która zaczyna się od **Strona-001**. Tym razem utworzony rekord strony to **Strona-001** typu **Osoba**. Po zsynchronizowaniu tych danych aplikacje Finance and Operations będą wyświetlać poprzedni komunikat o błędzie, ponieważ rekord strony **Strona-001** typu **Organizacja**.

Aby rozwiązać ten problem, zmień automatyczną sekwencję numerów dla pola **msdyn_partynumber** tabeli **msdyn_party** w usłudze Dataverse na inną automatyczną sekwencję numerów.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Problem z wydajnością mapowań klientów lub osób kontaktowych

Można uzyskać niewielką poprawę wydajności synchronizacji na żywo dla klientów i kontaktów, dostosowując metodę **getEntityDataSourceToFieldMapping** (w encji **CustCustomerV3Entity**) i metodę **getEntityDataSourceToFieldMapping** (w encji **smmContactPersonCDSV2Entity**). Te dostosowania redukują liczbę rekordów w tabeli **BusinessEventsDefinition**. Ta redukcja liczby rekordów zmniejsza z kolei liczbę wywoływanych zdarzeń.

Metoda **getEntityDataSourceToFieldMapping** w encji **CustCustomerV3Entity** zapewnia, że aktualizacja adresu elektronicznego lub adresu pocztowego klienta wyzwala zdarzenia biznesowe, dzięki czemu zaktualizowane dane zostaną wysłane do usługi Dataverse. Jeśli nie używasz wszystkich pól i informacje nie są potrzebne w trybie podwójnego zapisu, skomentuj odpowiednie wiersze w metodzie. Każde śledzone pole i tabela dodane do tej metody dodają rekord w tabeli **BusinessEventsDefinition** dla kombinacji śledzonej tabeli i śledzonej encji.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

Podbonie metoda **getEntityDataSourceToFieldMapping** w encji **smmContactPersonCDSV2Entity** zapewnia, że aktualizacja adresu elektronicznego lub adresu pocztowego wyzwala zdarzenia biznesowe, dzięki czemu zaktualizowane dane zostaną wysłane do usługi Dataverse. W tej metodzie można skomentować wiersze we wszystkich nieużywanych polach.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

Po zaktualizowaniu metod wykonaj poniższe kroki.

1. Zsynchronizuj bazę danych i skompiluj aplikację.
2. Zatrzymaj wszystkie mapy podwójnego zapisu utworzone w encjacj **smmContactPersonCDSV2Entity** i **CustCustomerV3Entity**.
3. Uruchom mapy. W encjach **smmContactPersonCDSV2Entity** i **CustCustomerV3Entity** powinno być mniej rekordów, a tabela **BusinessEventsDefinition** i wydajność mogą się nieznacznie poprawić.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

---
title: Optymalizowanie zapytań tabeli wirtualnej usługi Dataverse
description: Optymalizuj i rozwiązuj problemy z wydajnością zapytań do wirtualnych tabel Dataverse
author: twheeloc
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1f379cd7783cc984666582d2c680a1db013627ce
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070181"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Optymalizowanie zapytań tabeli wirtualnej usługi Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Wystawienie

### <a name="overview"></a>Omówienie

Podczas korzystania z tabel wirtualnych Dataverse do opracowywania integracji i innych połączeń danych z Dynamics 365 Human Resources, możesz napotkać problemy z wydajnością podczas wykonywania zapytań dotyczących tabel wirtualnych. Spowolnienie wykonywania kwerendy może mieć miejsce na różnych klientach lub interfejsach. Możesz na przykład wystąpić problem w następujących okolicznościach:

- Podczas wysyłania zapytań do wirtualnej tabeli za pośrednictwem interfejsu API sieci Web Dataverse
- Podczas tworzenia aplikacji Power App w tabeli wirtualnej
- Podczas tworzenia raportu Power BI w tabeli wirtualnej

Wszystkie te interfejsy mogą potencjalnie ujawnić problem z wydajnością.

Jedną z przyczyn niskiej wydajności tabel wirtualnych Dataverse dla Human Resources są kolumny kluczy obcych w tabeli wirtualnej związane z właściwościami [nawigacji tabeli](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties). Podczas tworzenia właściwości nawigacji dla tabeli wirtualnej kolumna klucza obcego jest automatycznie dodawana do tabeli, aby reprezentować wartość klucza dla kolumny klucza powiązanej tabeli wirtualnej. Na przykład kolumna **_mshr_fk_person_id_value** jest dodawana do jednostki **mshr_hcmworkerbaseentity** właściwości klucza obcego z jednostki **mshr_dirpersonentity**. Ze względu na sposób, w jaki wartości tych kolumn klucza obcego są przechowywane w tabeli, pobieranie wartości może mieć negatywny wpływ na wydajność zapytania względem tabeli wirtualnej.

### <a name="potential-symptoms"></a>Potencjalne objawy

Przykład, w którym można zobaczyć ten wpływ jest w kwerendach dotyczących jednostki Pracownik (**mshr_hcmworkerentity**) lub Pracownik podstawowy (**mshr_hcmworkerbaseentity**). Manifest problemu z wydajnością może być wyświetlony na kilka sposobów:

- **Wolno wykonywanie kwerendy**: Wykonywanie zapytania względem tabeli wirtualnej może spowodować zwrócenie oczekiwanych wyników, ale jego wykonanie może potrwać dłużej niż oczekiwano.
- **Limit czasu kwerendy**: Zapytanie może przekroczyć limit czasu i zwrócić następujący błąd: „Uzyskano token w celu wywołania aplikacji finansowych i operacyjnych, ale aplikacje finansowe i operacyjne zwróciły błąd typu InternalServerError”.
- **Nieoczekiwany błąd**: Zapytanie może zwrócić błąd typu 400 z następującym komunikatem: „Wystąpił nieoczekiwany błąd”.

  ![Typ błędu 400 w HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType400.png)

- **Ograniczenie wydajności**: Zapytanie może nadużywać zasobów serwera i podlegać ograniczeniom. W tym przypadku kwerenda zwraca następujący błąd: „Uzyskano token w celu wywołania aplikacji finansowych i operacyjnych, ale aplikacji finansowe i operacyjne zwróciły błąd typu 429”. Aby uzyskać więcej informacji dotyczących ograniczania wydajności w Human Resources, zobacz [Ograniczenie wydajności — często zadawane pytania](./hr-admin-integration-throttling-faq.md).

  ![Typ błędu 429 w HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Rozwiązanie

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Ograniczenie liczby kolumn w kwerendzie danych

W przypadku tabel wirtualnych jedną z metod o największym potencjale poprawy wydajności zapytań jest ograniczenie liczby kolumn wybranych w zapytaniu. Ogólne wskazówki dotyczące optymalizacji wydajności zapytań to ograniczenie kolumn zwracanych w zapytaniu tylko do tych właściwości, które są potrzebne. Jest to szczególnie prawdziwe w przypadku kolumn klucza obcego w tabelach wirtualnych. Jeśli nie potrzebujesz wartości w kolumnach klucza obcego do integracji lub raportu, skonfiguruj zapytanie tak, aby wybrało tylko te kolumny, których potrzebujesz, z wyłączeniem kolumn klucza obcego.

#### <a name="selecting-columns-in-an-odata-query"></a>Wybieranie kolumn w kwerendzie OData

Podczas odpytywania tabeli wirtualnej za pośrednictwem interfejsu API sieci Web Dataverse można ograniczyć liczbę kolumn zawartych w zapytaniu za pomocą opcji zapytania systemowego **$select** i zdefiniować kolumny, dla których mają być zwracane wyniki. Aby zmaksymalizować wydajność, wyklucz kolumny kluczy obcych (te z prefiksem **_mshr_FK_**) z zapytania.

Na przykład następujące zapytanie dotyczące jednostki **mshr_hcmworkerbaseentity** będzie zawierać tylko kolumny zawarte w klauzuli opcji **$select** kwerendy, z wyłączeniem wartości klucza obcego. Zapewnia to znaczną poprawę wydajności w porównaniu z zapytaniem zawierającym wszystkie kolumny tabeli.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Zalecenie ograniczenia liczby wybranych kolumn ma również zastosowanie w przypadku korzystania z opcji zapytania **$expand** w celu rozszerzenia zapytania na powiązane tabele wirtualne za pomocą właściwości nawigacji. Na przykład następująca kwerenda zawiera kolumny **mshr_hcmworkerbaseentity** jednostki z rozszerzonymi kolumnami jednostki **mshr_dirpersonentity**. Należy zauważyć, opcja kwerendy **$select** jest także uwzględniona w opcji kwerendy **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Korzystając z tej metody pobierania danych z opcją zapytania **$select** w klauzuli opcji zapytania **$expand**, zwykle można zauważyć większą poprawę wydajności, gdy właściwość nawigacji między jednostkami to realcja wiele-do-jednego. Podczas rozwijania relacji jeden-do-wielu nie widać tego samego zmniejszenia czasu wykonywania kwerendy. Aby uzyskać więcej informacji na temat definicji relacji tabel wirtualnych Dataverse, zobacz temat [Relacje tabel](/powerapps/maker/data-platform/create-edit-entity-relationships).

Aby uzyskać więcej informacji dotyczących używania kwerend systemowych **$select** i **$expand** w interfejsie API sieci Web Dataverse, zobacz temat [Pobierz rekordy jednostek pokrewnych za pomocą zapytania](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Wybieranie kolumn w Power BI

Jeśli napotkasz jakiekolwiek z wyżej wymienionych oznak niskiej wydajności podczas tworzenia raportu usługi Power BI na podstawie tabeli wirtualnej Dataverse, możesz zwiększyć wydajność, wykluczając kolumny klucza obcego z kolumn wybranych z tabeli do raportu. Na przykład jeśli używasz programu Power BI Desktop do tworzenia raportu dla encji **mshr_hcmworkerbaseentity**, możesz wykonać następujące kroki, aby wybrać kolumny, które chcesz uwzględnić w zapytaniu raportu.

1. W Power BI Desktop wybierz pozycję **Więcej...** z listy rozwijanej **Pobierz dane** na wstążce akcji.
2. W oknie **Pobierz dane** wprowadź w polu wyszukiwania **Common Data Service** i wybierz łącznik **Common Data Service**, a następnie wybierz **Połącz**.
3. W polu **Adres URL serwera** w oknie Common Data Service wprowadź adres URI organizacji w swoim środowisku Dataverse i wybierz przycisk **OK**.
  
   ![Wprowadź identyfikator URI dla swojego środowiska Dataverse.](./media/PowerBIDataverseURLSetup.png)
  
4. W oknie Nawiguj po rozwinięciu węzła **Jednostki**.
5. W polu wyszukiwania wprowadź **mshr_hcmworkerbaseentity** i wybierz jednostkę.
6. Wybierz **Przekształć dane**.
7. W oknie Edytor Power Query wybierz opcję **Zaawansowany edytor**.
8. W oknie **Edytor zaawansowany** zaktualizuj kwerendę, tak aby była wyglądać jak poniżej, dodając lub usuwając w razie potrzeby kolumny do tablicy.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Zaktualizuj zapytanie w Edytorze zaawansowanym dla Edytora Power Query.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Wybierz opcję **Gotowe**.

   > [!NOTE]
   > Jeśli wcześniej otrzymałeś błąd typu 429 z zapytania przed aktualizacją, może być konieczne poczekanie na okres ponowienia przed odświeżeniem zapytania, aby zakończyło się pomyślnie.

10. Kliknij przycisk **Zamknij i Zastosuj** na wstążce akcji Edytor Power Query.

Następnie możesz rozpocząć tworzenie raportu usługi Power BI na podstawie kolumn wybranych z tabeli wirtualnej.

#### <a name="selecting-columns-in-power-apps"></a>Wybieranie kolumn w Power Apps

Podobnie jak w przypadku zapytań interfejsu API sieci Web Dataverse i usługi Power BI, można zwiększyć wydajność zapytań dla Power Apps w oparciu o tabele wirtualne Dataverse, wykluczając kolumny powiązanych tabel z aplikacji. Jeśli na stronie znajdują się kolumny z powiązanej tabeli, adres URL żądania utworzony w celu pobrania danych będzie zawierał właściwości klucza obcego powiązanej tabeli. Ten element, tak jak w przykładach opcji [Wybieranie kolumn w kwerendzie OData](#selecting-columns-in-power-apps) powyżej, zmniejsza wydajność, powodując dodatkowe wyszukiwania danych.

Aby obejść ten problem, możesz sprawdzić, czy żadne pola danych z powiązanych tabel nie zostały uwzględnione w żadnym formularzu danych aplikacji Power App.

1. W okienku Widok drzewa wybierz formularz danych na ekranie.
2. W panelu **Właściwości** wybierz pozycję **Edytuj** we właściwości **Pola**.
3. W okienku **Dane** sprawdź, czy żadne z wybranych pól nie jest polami tabeli wirtualnej źródła danych.

Jeśli na przykład jedno z pól danych zawartych na stronie aplikacji odwołuje się do innej tabeli, na przykład **ThisItem.Worker.Name**, w której **Pracownik** jest tabelą powiązaną, istnieje możliwość zmniejszenia wydajności pobierania danych.

Za pomocą [monitora Power Apps](/powerapps/maker/monitor-overview) można upewnić się, że w kwerendzie są uwzględniane tylko kolumny potrzebne do uzyskania danych dotyczących aplikacji Power App. Możesz wyświetlić adres URL utworzony dla operacji getRows, aby upewnić się, że kolumny wybrane dla Twojej aplikacji będą optymalne do pobierania danych.

![Użyj monitora Power Apps do analizy operacji getData.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtrowanie kwerendy danych

Inną metodą poprawy wydajności wykonywania zapytań jest ograniczenie liczby rekordów zwracanych w wynikach zapytania. Możesz to zrobić, filtrując wyniki, aby mieć pewność, że otrzymujesz tylko potrzebne rekordy.

Aby uzyskać więcej informacji o filtrowaniu danych kwerend, zobacz temat [Wyniki filtru](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results).

### <a name="limiting-the-page-size-of-the-query"></a>Ograniczenie rozmiaru strony kwerendy

Jeśli pracujesz z dużymi zbiorami danych, możesz podzielić wyniki zapytania na wiele stron, dodając nagłówek preferencji `odata.maxpagesize` do zapytań o dane.

Aby uzyskać więcej informacji na temat stronicowania, zobacz temat [Określ liczbę jednostek do zwrócenia na stronie](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Informacje dodatkowe

- [Konfiguruj tabele wirtualne usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
- [Tabele wirtualne usługi Human Resources — często zadawane pytania](hr-admin-virtual-entity-faq.md)
- [Dławienie — często zadawane pytania](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]


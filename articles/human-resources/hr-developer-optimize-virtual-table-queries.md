---
title: Optymalizowanie zapytań tabeli wirtualnej usługi Dataverse
description: Optymalizuj i rozwiązuj problemy z wydajnością zapytań do wirtualnych tabel Dataverse
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66fb9f2b50079b5eb4eb16da17b8a473d687d354
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054915"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="9c787-103">Optymalizowanie zapytań tabeli wirtualnej usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c787-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="9c787-104">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="9c787-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="9c787-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9c787-105">Overview</span></span>

<span data-ttu-id="9c787-106">Podczas korzystania z tabel wirtualnych Dataverse do opracowywania integracji i innych połączeń danych z Dynamics 365 Human Resources, możesz napotkać problemy z wydajnością podczas wykonywania zapytań dotyczących tabel wirtualnych.</span><span class="sxs-lookup"><span data-stu-id="9c787-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="9c787-107">Spowolnienie wykonywania kwerendy może mieć miejsce na różnych klientach lub interfejsach.</span><span class="sxs-lookup"><span data-stu-id="9c787-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="9c787-108">Możesz na przykład wystąpić problem w następujących okolicznościach:</span><span class="sxs-lookup"><span data-stu-id="9c787-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="9c787-109">Podczas wysyłania zapytań do wirtualnej tabeli za pośrednictwem interfejsu API sieci Web Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c787-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="9c787-110">Podczas tworzenia aplikacji Power App w tabeli wirtualnej</span><span class="sxs-lookup"><span data-stu-id="9c787-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="9c787-111">Podczas tworzenia raportu Power BI w tabeli wirtualnej</span><span class="sxs-lookup"><span data-stu-id="9c787-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="9c787-112">Wszystkie te interfejsy mogą potencjalnie ujawnić problem z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="9c787-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="9c787-113">Jedną z przyczyn niskiej wydajności tabel wirtualnych Dataverse dla Human Resources są kolumny kluczy obcych w tabeli wirtualnej związane z właściwościami [nawigacji tabeli](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span><span class="sxs-lookup"><span data-stu-id="9c787-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="9c787-114">Podczas tworzenia właściwości nawigacji dla tabeli wirtualnej kolumna klucza obcego jest automatycznie dodawana do tabeli, aby reprezentować wartość klucza dla kolumny klucza powiązanej tabeli wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="9c787-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="9c787-115">Na przykład kolumna **_mshr_fk_person_id_value** jest dodawana do jednostki **mshr_hcmworkerbaseentity** właściwości klucza obcego z jednostki **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="9c787-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="9c787-116">Ze względu na sposób, w jaki wartości tych kolumn klucza obcego są przechowywane w tabeli, pobieranie wartości może mieć negatywny wpływ na wydajność zapytania względem tabeli wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="9c787-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="9c787-117">Potencjalne objawy</span><span class="sxs-lookup"><span data-stu-id="9c787-117">Potential symptoms</span></span>

<span data-ttu-id="9c787-118">Przykład, w którym można zobaczyć ten wpływ jest w kwerendach dotyczących jednostki Pracownik (**mshr_hcmworkerentity**) lub Pracownik podstawowy (**mshr_hcmworkerbaseentity**).</span><span class="sxs-lookup"><span data-stu-id="9c787-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="9c787-119">Manifest problemu z wydajnością może być wyświetlony na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="9c787-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="9c787-120">**Wolno wykonywanie kwerendy**: Wykonywanie zapytania względem tabeli wirtualnej może spowodować zwrócenie oczekiwanych wyników, ale jego wykonanie może potrwać dłużej niż oczekiwano.</span><span class="sxs-lookup"><span data-stu-id="9c787-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="9c787-121">**Limit czasu kwerendy**: Zapytanie może przekroczyć limit czasu i zwrócić następujący błąd: „Uzyskano token w celu wywołania Finance and Operations, ale Finance and Operations zwrócił błąd typu InternalServerError”.</span><span class="sxs-lookup"><span data-stu-id="9c787-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="9c787-122">**Nieoczekiwany błąd**: Zapytanie może zwrócić błąd typu 400 z następującym komunikatem: „Wystąpił nieoczekiwany błąd”.</span><span class="sxs-lookup"><span data-stu-id="9c787-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![Typ błędu 400 w HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="9c787-124">**Ograniczenie wydajności**: Zapytanie może nadużywać zasobów serwera i podlegać ograniczeniom.</span><span class="sxs-lookup"><span data-stu-id="9c787-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="9c787-125">W tym przypadku kwerenda zwraca następujący błąd: „Uzyskano token w celu wywołania Finance and Operations, ale Finance and Operations zwrócił błąd typu 429”.</span><span class="sxs-lookup"><span data-stu-id="9c787-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="9c787-126">Aby uzyskać więcej informacji dotyczących ograniczania wydajności w Human Resources, zobacz [Ograniczenie wydajności — często zadawane pytania](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9c787-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![Typ błędu 429 w HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="9c787-128">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="9c787-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="9c787-129">Ograniczenie liczby kolumn w kwerendzie danych</span><span class="sxs-lookup"><span data-stu-id="9c787-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="9c787-130">W przypadku tabel wirtualnych jedną z metod o największym potencjale poprawy wydajności zapytań jest ograniczenie liczby kolumn wybranych w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="9c787-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="9c787-131">Ogólne wskazówki dotyczące optymalizacji wydajności zapytań to ograniczenie kolumn zwracanych w zapytaniu tylko do tych właściwości, które są potrzebne.</span><span class="sxs-lookup"><span data-stu-id="9c787-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="9c787-132">Jest to szczególnie prawdziwe w przypadku kolumn klucza obcego w tabelach wirtualnych.</span><span class="sxs-lookup"><span data-stu-id="9c787-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="9c787-133">Jeśli nie potrzebujesz wartości w kolumnach klucza obcego do integracji lub raportu, skonfiguruj zapytanie tak, aby wybrało tylko te kolumny, których potrzebujesz, z wyłączeniem kolumn klucza obcego.</span><span class="sxs-lookup"><span data-stu-id="9c787-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="9c787-134">Wybieranie kolumn w kwerendzie OData</span><span class="sxs-lookup"><span data-stu-id="9c787-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="9c787-135">Podczas odpytywania tabeli wirtualnej za pośrednictwem interfejsu API sieci Web Dataverse można ograniczyć liczbę kolumn zawartych w zapytaniu za pomocą opcji zapytania systemowego **$select** i zdefiniować kolumny, dla których mają być zwracane wyniki.</span><span class="sxs-lookup"><span data-stu-id="9c787-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="9c787-136">Aby zmaksymalizować wydajność, wyklucz kolumny kluczy obcych (te z prefiksem **_mshr_FK_**) z zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c787-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="9c787-137">Na przykład następujące zapytanie dotyczące jednostki **mshr_hcmworkerbaseentity** będzie zawierać tylko kolumny zawarte w klauzuli opcji **$select** kwerendy, z wyłączeniem wartości klucza obcego.</span><span class="sxs-lookup"><span data-stu-id="9c787-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="9c787-138">Zapewnia to znaczną poprawę wydajności w porównaniu z zapytaniem zawierającym wszystkie kolumny tabeli.</span><span class="sxs-lookup"><span data-stu-id="9c787-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="9c787-139">Zalecenie ograniczenia liczby wybranych kolumn ma również zastosowanie w przypadku korzystania z opcji zapytania **$expand** w celu rozszerzenia zapytania na powiązane tabele wirtualne za pomocą właściwości nawigacji.</span><span class="sxs-lookup"><span data-stu-id="9c787-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="9c787-140">Na przykład następująca kwerenda zawiera kolumny **mshr_hcmworkerbaseentity** jednostki z rozszerzonymi kolumnami jednostki **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="9c787-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="9c787-141">Należy zauważyć, opcja kwerendy **$select** jest także uwzględniona w opcji kwerendy **$expand**.</span><span class="sxs-lookup"><span data-stu-id="9c787-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="9c787-142">Korzystając z tej metody pobierania danych z opcją zapytania **$select** w klauzuli opcji zapytania **$expand**, zwykle można zauważyć większą poprawę wydajności, gdy właściwość nawigacji między jednostkami to realcja wiele-do-jednego.</span><span class="sxs-lookup"><span data-stu-id="9c787-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="9c787-143">Podczas rozwijania relacji jeden-do-wielu nie widać tego samego zmniejszenia czasu wykonywania kwerendy.</span><span class="sxs-lookup"><span data-stu-id="9c787-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="9c787-144">Aby uzyskać więcej informacji na temat definicji relacji tabel wirtualnych Dataverse, zobacz temat [Relacje tabel](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="9c787-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="9c787-145">Aby uzyskać więcej informacji dotyczących używania kwerend systemowych **$select** i **$expand** w interfejsie API sieci Web Dataverse, zobacz temat [Pobierz rekordy jednostek pokrewnych za pomocą zapytania](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="9c787-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="9c787-146">Wybieranie kolumn w Power BI</span><span class="sxs-lookup"><span data-stu-id="9c787-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="9c787-147">Jeśli napotkasz jakiekolwiek z wyżej wymienionych oznak niskiej wydajności podczas tworzenia raportu usługi Power BI na podstawie tabeli wirtualnej Dataverse, możesz zwiększyć wydajność, wykluczając kolumny klucza obcego z kolumn wybranych z tabeli do raportu.</span><span class="sxs-lookup"><span data-stu-id="9c787-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="9c787-148">Na przykład jeśli używasz programu Power BI Desktop do tworzenia raportu dla encji **mshr_hcmworkerbaseentity**, możesz wykonać następujące kroki, aby wybrać kolumny, które chcesz uwzględnić w zapytaniu raportu.</span><span class="sxs-lookup"><span data-stu-id="9c787-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="9c787-149">W Power BI Desktop wybierz pozycję **Więcej...** z listy rozwijanej **Pobierz dane** na wstążce akcji.</span><span class="sxs-lookup"><span data-stu-id="9c787-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="9c787-150">W oknie **Pobierz dane** wprowadź w polu wyszukiwania **Common Data Service** i wybierz łącznik **Common Data Service**, a następnie wybierz **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="9c787-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="9c787-151">W polu **Adres URL serwera** w oknie Common Data Service wprowadź adres URI organizacji w swoim środowisku Dataverse i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c787-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Wprowadź identyfikator URI dla swojego środowiska Dataverse](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="9c787-153">W oknie Nawiguj po rozwinięciu węzła **Jednostki**.</span><span class="sxs-lookup"><span data-stu-id="9c787-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="9c787-154">W polu wyszukiwania wprowadź **mshr_hcmworkerbaseentity** i wybierz jednostkę.</span><span class="sxs-lookup"><span data-stu-id="9c787-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="9c787-155">Wybierz **Przekształć dane**.</span><span class="sxs-lookup"><span data-stu-id="9c787-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="9c787-156">W oknie Edytor Power Query wybierz opcję **Zaawansowany edytor**.</span><span class="sxs-lookup"><span data-stu-id="9c787-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="9c787-157">W oknie **Edytor zaawansowany** zaktualizuj kwerendę, tak aby była wyglądać jak poniżej, dodając lub usuwając w razie potrzeby kolumny do tablicy.</span><span class="sxs-lookup"><span data-stu-id="9c787-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Zaktualizuj zapytanie w Edytorze zaawansowanym dla Edytora Power Query](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="9c787-159">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="9c787-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c787-160">Jeśli wcześniej otrzymałeś błąd typu 429 z zapytania przed aktualizacją, może być konieczne poczekanie na okres ponowienia przed odświeżeniem zapytania, aby zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="9c787-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="9c787-161">Kliknij przycisk **Zamknij i Zastosuj** na wstążce akcji Edytor Power Query.</span><span class="sxs-lookup"><span data-stu-id="9c787-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="9c787-162">Następnie możesz rozpocząć tworzenie raportu usługi Power BI na podstawie kolumn wybranych z tabeli wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="9c787-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="9c787-163">Wybieranie kolumn w Power Apps</span><span class="sxs-lookup"><span data-stu-id="9c787-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="9c787-164">Podobnie jak w przypadku zapytań interfejsu API sieci Web Dataverse i usługi Power BI, można zwiększyć wydajność zapytań dla Power Apps w oparciu o tabele wirtualne Dataverse, wykluczając kolumny powiązanych tabel z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9c787-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="9c787-165">Jeśli na stronie znajdują się kolumny z powiązanej tabeli, adres URL żądania utworzony w celu pobrania danych będzie zawierał właściwości klucza obcego powiązanej tabeli.</span><span class="sxs-lookup"><span data-stu-id="9c787-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="9c787-166">Ten element, tak jak w przykładach opcji [Wybieranie kolumn w kwerendzie OData](#selecting-columns-in-power-apps) powyżej, zmniejsza wydajność, powodując dodatkowe wyszukiwania danych.</span><span class="sxs-lookup"><span data-stu-id="9c787-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="9c787-167">Aby obejść ten problem, możesz sprawdzić, czy żadne pola danych z powiązanych tabel nie zostały uwzględnione w żadnym formularzu danych aplikacji Power App.</span><span class="sxs-lookup"><span data-stu-id="9c787-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="9c787-168">W okienku Widok drzewa wybierz formularz danych na ekranie.</span><span class="sxs-lookup"><span data-stu-id="9c787-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="9c787-169">W panelu **Właściwości** wybierz pozycję **Edytuj** we właściwości **Pola**.</span><span class="sxs-lookup"><span data-stu-id="9c787-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="9c787-170">W okienku **Dane** sprawdź, czy żadne z wybranych pól nie jest polami tabeli wirtualnej źródła danych.</span><span class="sxs-lookup"><span data-stu-id="9c787-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="9c787-171">Jeśli na przykład jedno z pól danych zawartych na stronie aplikacji odwołuje się do innej tabeli, na przykład **ThisItem.Worker.Name**, w której **Pracownik** jest tabelą powiązaną, istnieje możliwość zmniejszenia wydajności pobierania danych.</span><span class="sxs-lookup"><span data-stu-id="9c787-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="9c787-172">Za pomocą [monitora Power Apps](/powerapps/maker/monitor-overview) można upewnić się, że w kwerendzie są uwzględniane tylko kolumny potrzebne do uzyskania danych dotyczących aplikacji Power App.</span><span class="sxs-lookup"><span data-stu-id="9c787-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="9c787-173">Możesz wyświetlić adres URL utworzony dla operacji getRows, aby upewnić się, że kolumny wybrane dla Twojej aplikacji będą optymalne do pobierania danych.</span><span class="sxs-lookup"><span data-stu-id="9c787-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![Użyj monitora Power Apps do analizy operacji getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="9c787-175">Filtrowanie kwerendy danych</span><span class="sxs-lookup"><span data-stu-id="9c787-175">Filtering the data query</span></span>

<span data-ttu-id="9c787-176">Inną metodą poprawy wydajności wykonywania zapytań jest ograniczenie liczby rekordów zwracanych w wynikach zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c787-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="9c787-177">Możesz to zrobić, filtrując wyniki, aby mieć pewność, że otrzymujesz tylko potrzebne rekordy.</span><span class="sxs-lookup"><span data-stu-id="9c787-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="9c787-178">Aby uzyskać więcej informacji o filtrowaniu danych kwerend, zobacz temat [Wyniki filtru](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results).</span><span class="sxs-lookup"><span data-stu-id="9c787-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="9c787-179">Ograniczenie rozmiaru strony kwerendy</span><span class="sxs-lookup"><span data-stu-id="9c787-179">Limiting the page size of the query</span></span>

<span data-ttu-id="9c787-180">Jeśli pracujesz z dużymi zbiorami danych, możesz podzielić wyniki zapytania na wiele stron, dodając nagłówek preferencji `odata.maxpagesize` do zapytań o dane.</span><span class="sxs-lookup"><span data-stu-id="9c787-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="9c787-181">Aby uzyskać więcej informacji na temat stronicowania, zobacz temat [Określ liczbę jednostek do zwrócenia na stronie](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="9c787-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c787-182">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9c787-182">See also</span></span>

- [<span data-ttu-id="9c787-183">Konfiguruj tabele wirtualne usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c787-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="9c787-184">Tabele wirtualne usługi Human Resources — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="9c787-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="9c787-185">Dławienie — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="9c787-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
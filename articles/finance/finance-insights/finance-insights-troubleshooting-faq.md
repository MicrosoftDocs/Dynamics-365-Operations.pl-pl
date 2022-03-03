---
title: Rozwiązywanie problemów z ustawieniami Finance insights
description: W tym temacie wymieniono problemy, które mogą wystąpić, gdy są dostępne funkcje analizy Finance insights. Opisano w nim również sposób rozwiązania tych problemów.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: fc616e5fce6bbfeaa3b36ccc35f1b1cf407af4a6
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109867"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Rozwiązywanie problemów z ustawieniami Finance insights

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono problemy, które mogą wystąpić, gdy są dostępne funkcje analizy Finance insights. Opisano w nim również sposób rozwiązania tych problemów.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Symptom: Dlaczego nie mogę zmapować kolumny docelowej szablonu Integracja danych szczegółowych informacji o płatnościach klienta?

### <a name="resolution"></a>Rozwiązanie

Być może używasz szablonu dla wcześniejszej wersji. Przed wydaniem wersji 10.0.17 klienci korzystający z wersji zapoznawczej skonfigurowali szablon **Wyniki analizy płatności klientów (CDS do Fin and Ops)** Integracja danych (DI) przy użyciu encji **Wynik prognozy płatności (wersja zapoznawcza)** . Po uaktualnieniu do wersji 10.0.17 i nowszych do ukończenia mapowania użyj szablonu **Informacje o płatnościach klientów (z CDS do Fin and Ops 10.0.17 i nowszych)**. Możesz nie być w stanie zmapować kolumny docelowej szablonu DI, dopóki lista encji zarządzania danymi nie zostanie odświeżona i pojawi się w niej encja **Wynik prognozy płatności**. Aby odświeżyć listę encji i wyświetlić wynik prognozy płatności, wykonaj kroki w Microsoft Dynamics 365 Finance i Dataverse (wcześniej znanym jako portal administracyjny Common Data Service \[CDS\]).

### <a name="in-finance"></a>W Finance

Po uaktualnieniu wykonaj kroki opisane w te czynnościach w instrukcje Finanse.

1. Wybierz kolejno opcje **Administrowanie systemem \> Obszary robocze \> Zarządzanie danymi**.
2. W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Ustawienia ramowe**.
3. Na stronie **Parametry importu/eksportu danych** wybierz **Ustawienia jednostki**, a następnie wybierz pozycję **Odśwież listę jednostek**.
4. Zamknij stronę **Parametry struktury importu/eksportu danych**.
5. W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Jednostki danych**.
6. Wyszukaj wynik prognozy płatności Sprawdź, czy **jednostka Wynik prognozy płatności** nie jest wersją podglądu. Nazwa wersji zapoznawczej kończy się na „(preview)” Jeśli masz tylko wersję zapoznawczą jednostki, skontaktuj się z Pomocą techniczną firmy Microsoft.

### <a name="in-dataverse"></a>W Dataverse

Aby zaktualizować projekty integracji danych, wykonaj kroki opisane w [Centrum administratora Power Platform](https://admin.powerplatform.microsoft.com/environments).

1. Jeśli korzystasz z wersji zapoznawczej Finance insights, usuń projekt DI powiązany z szablonem **Wyniki statystyk płatności klientów (z CDS do Fin and Ops)**.
2. Wykonaj kroki w tece [Tworzenie projektu integratora danych](create-data-integrate-project.md). Użyj szablonu **Wyniki statystyk płatności klientów (z CDS do Fin and Ops 10.0.17 i nowszych)**.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Objaw: Dlaczego przy próbie otwarcia AI Builder za pomocą łączy na stronie konfiguracji prognozy płatności odbiorcy pojawia się następujący komunikat o błędzie: „Niestety, wystąpiło rozłączenie"?

### <a name="resolution"></a>Rozwiązanie

Użytkownicy Dynamics 365 Finance muszą mieć konto użytkownika Microsoft Power Apps dla środowiska, a to konto użytkownika musi mieć rolę Konfigurator systemu. Administrator systemu Microsoft Power Apps może utworzyć konto użytkownika i przypisać rolę. Następnie można przejść do systemu, zalogować się na <https://make.preview.powerapps.com/> przy użyciu tego konta użytkownika i spróbować ponownie użyć łączy.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Objaw: Dlaczego na karcie Prognoza gotówki w obszarze roboczym Prognoza przepływów pieniężnych nie są wyświetlane jakiekolwiek dane?

### <a name="resolution"></a>Rozwiązanie

Aby poprawnie wyświetlać dane w obszarze roboczym **Prognoza przepływów pieniężnych**, należy skonfigurować i włączyć funkcję prognozowania przepływów pieniężnych w Zarządzaniu środkami pieniężnymi i bankami oraz funkcję Prognozy przepływów pieniężnych w Finance insights.

Najpierw skonfiguruj i włącz prognozowanie przepływów pieniężnych oraz konta płynności. Aby uzyskać więcej informacji, zobacz [Prognozowanie przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md). Jeśli konfiguracja została zakończona, ale nie widzisz oczekiwanych wyników, zobacz [Rozwiązywanie problemów z konfiguracją prognozowania przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting-tsg.md), aby uzyskać więcej informacji.

Następnie potwierdź, że funkcja Prognozy przepływów pieniężnych w danych finansowych (**Zarządzanie gotówką i bankami \> Ustawienia \> Finance Insights \> Prognozy przepływów pieniężnych**) została włączona, a szkolenie modelu AI zostało ukończone. Jeśli szkolenie nie zostało ukończone, wybierz opcję **Prognoza teraz**, aby rozpocząć proces szkoleniowy modelu.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Objaw: dlaczego nie widać przycisku Zainstaluj nowy dodatek w usłudze Microsoft Dynamics Lifecycle Services?

### <a name="resolution"></a>Rozwiązanie

Najpierw sprawdź, czy rola **Menedżer środowiska** lub **Właściciel projektu** jest przypisana do zalogowano użytkownika w polu **Rola zabezpieczeń projektu** w usłudze Microsoft Dynamics Lifecycle Services (LCS). Instalacja nowych dodatków wymaga jednej z tych ról zabezpieczeń projektu.

Jeśli zostanie użytkownikowi przypisana poprawna rola zabezpieczeń projektu, może być konieczne odświeżenie okna przeglądarki, aby zobaczyć przycisk **Zainstaluj nowy dodatek**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Objaw: Wygląda na to, że dodatek Finance Insights nie jest instalowany. Dlaczego?

### <a name="resolution"></a>Rozwiązanie

Należy wykonać następujące kroki.

- Sprawdź, czy masz dostęp do opcji **Administrator systemu** i **Dostosowanie systemu** w Centrum administratora programu Power Portal.
- Sprawdź, czy do użytkownika, który instaluje ten dodatek, ma zastosowanie licencja Dynamics 365 Finance lub równoważna.
- Sprawdź, czy w poniższa aplikacja Azure AD jest zarejestrowana w usłudze Azure AD: 

  | Zgłoszenie                  | Identyfikator aplikacji           |
  | ---------------------------- | ---------------- |
  | CDS mikrousług ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Symptom: Błąd: „Nie znaleźliśmy żadnych danych dla wybranego zakresu filtrów. Wybierz inny zakres filtru i spróbuj ponownie”. 

### <a name="resolution"></a>Rozwiązanie

Sprawdź ustawienia integratora danych, aby upewnić się, że działa on zgodnie z oczekiwaniami i wstawia dane z AI Builder z powrotem do Finance.  
Aby uzyskać więcej informacji, zobacz temat [Utwórz projekt integracji danych](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Symptom: Trening przewidywania płatności klienta nie powiódł się, a błąd AI Builder mówi: „Przewidywanie powinno mieć tylko 2 różne wartości wyniku, aby wytrenować model. Mapuj do dwóch wyników i przekwalifikuj się”, „Problem z raportem szkoleniowym: IsNotMinRequiredDistinctNonNullValues”.

### <a name="resolution"></a>Rozwiązanie

Ten błąd oznacza, że w ostatnim roku nie ma wystarczającej liczby historycznych transakcji, które reprezentują każdą z kategorii opisanych w kategoriach **Na czas**, **Późno** i **Bardzo późno**. Aby rozwiązać ten błąd, dostosuj **okres bardzo późnej transakcji**. Jeśli ustawienie **Bardzo późnego** okresu transakcji nie naprawi błędu, **Przewidywanie płatności klientów** nie jest najlepszym rozwiązaniem, ponieważ wymaga danych w każdej kategorii do celów szkoleniowych.

Więcej informacji o tym, jak dostosować kategorie **Na czas**, **Późno** i **Bardzo późno** znajdziesz w [Włącz przewidywania płatności klienta](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Symptom: Trening modelu nie powiódł się

### <a name="resolution"></a>Rozwiązanie

Uczenie modelu **Prognoza przepływów pieniężnych** wymaga danych zawierających 100 lub więcej transakcji obejmujących ponad rok. Zaleca się, aby mieć co najmniej dwa lata z ponad 1000 transakcji.

Funkcja **prognozy płatności odbiorcy** wymaga ponad 100 transakcji w ciągu ostatnich sześciu do 9 miesięcy. Transakcje mogą obejmować faktury tekstowe, zamówienia sprzedaży i płatności odbiorcy. Te dane muszą się rozłożyć na ustawieniach **Na czas**, **Późno** i **Bardzo późno** zdefiniowane na stronie **Konfiguracja**.    

Funkcja **propozycji budżetu** wymaga co najmniej trzech lat budżetów lub danych rzeczywistych. To rozwiązanie wykorzystuje w prognozach dane z trzech do dziesięciu lat. Więcej niż trzy lata przyniesie lepsze rezultaty. Same dane najlepiej działa w przypadku odchylenia wartości. Jeśli dane zawierają wszystkie stałe dane, takie jak wydatki na dzierżawę, szkolenie może się nie powieść, ponieważ brak odchylenia nie wymaga AI dla projektu kwot.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Objaw: Komunikat o błędzie wskazuje, że tabela o nazwie „msdyn_paypredpredictionresultentities” nie istnieje. Serwer zdalny zwrócił błąd: (404) Nie znaleziono.

### <a name="resolution"></a>Rozwiązanie

Środowisko osiągnęła limit maksymalnej liczby tabel usług Data Lake. Aby uzyskać więcej informacji dotyczących limitu, zobacz sekcję **Włącz zmiany danych** w pobliżu godzin rzeczywistych w tym temacie, [Omówienie eksportu do usługi Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).

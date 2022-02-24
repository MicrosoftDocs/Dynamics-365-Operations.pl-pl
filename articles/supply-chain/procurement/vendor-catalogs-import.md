---
title: Importowanie katalogów dostawców
description: W tym temacie opisano proces importowania danych katalogu dostawcy.
author: RichardLuan
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: riluan
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 6a6fc2b4fe4245a1fe5b5a7eaafe8cc7fd337ab9
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020761"
---
# <a name="import-vendor-catalogs"></a>Importowanie katalogów dostawców

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Importowanie katalogów dostawców

W programie Dynamics 365 Supply Chain Management specjaliści ds. zakupów mogą tworzyć i obsługiwać katalogi, z których pracownicy firmy mogą korzystać podczas składania zamówień na towary i usługi do użytku wewnętrznego. Aby utworzyć katalog zaopatrzenia, można dodać towary i usługi, które mają być udostępnione pracownikom, importując dane katalogu produktów lub ręczne dodając dane z katalogu produktów do produktu głównego. 

Można przekazać dane katalogu przesłane przez dostawcę z klienta programu Microsoft Dynamics 365.

Dane produktów przesłane przez dostawcę, w postaci pliku żądania zarządzania katalogiem (CMR), muszą być w formacie pliku XML. Plik CMR powinien zawierać szczegóły produktów dostarczanych przez dostawcę do firmy.

## <a name="import-vendor-catalog-data"></a>Importowanie danych katalogu dostawcy

Aby importować dane katalogu dostawcy, należy wykonać następujące zadania:

1. Skonfiguruj projekt w obszarze roboczym Zarządzanie danymi, gdzie zdefiniowano reguły mapowania danych. Wybierz opcję **Zarządzanie danymi**, a następnie wybierz opcję **Konfiguruj role dla projektów danych**.

2. Skonfiguruj hierarchię kategorii zaopatrzenia i przypisz dostawców do kategorii zaopatrzenia. Jeśli używasz kodów asortymentu, dodaj je do kategorii zaopatrzenia. Aby uzyskać informacje dotyczące konfigurowania hierarchii kategorii zaopatrzenia, zobacz [Ustawianie hierarchii kategorii zaopatrzenia](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Skonfiguruj dostawcę dla importu katalogu. Wybierz dostawcę, a następnie wybierz kolejno opcje **Zaopatrzenie** > **Konfiguracja** > **Konfigurowanie dostawcy dla importu katalogu**.

4. Skonfiguruj przepływ pracy importu katalogu. Utwórz szablon pliku CMR i udostępnij go dostawcy.

5. Wybierz kolejno opcje **Zaopatrzenie i sourcing** \> **Wspólne** \> **Katalogi** \> **Katalogi dostawców**, aby utworzyć katalog dostawcy. W tym katalogu będą grupowane pliki żądań zarządzania katalogami (CMR) otrzymywane od dostawcy. 

6. Przekaż plik CMR.

7. Przejrzyj i zatwierdź lub odrzuć produkty w katalogu dostawcy. Produkty zostaną automatycznie zamapowane na kategorie zaopatrzenia. 

Zatwierdzone produkty są dodawane do produktu głównego i zwalniane dla wybranych firm. Do katalogu zaopatrzenia można dodawać tylko zatwierdzone produkty.

## <a name="generate-a-catalog-import-file-template"></a>Generowanie szablonu pliku importu katalogu

Szablon pliku importu katalogu jest plikiem XSD służącym do utworzenia pliku CMR dla produktów dostawcy. Plik CMR można służyć do utworzenia nowego katalogu lub zastąpienia czy zmodyfikowania istniejącego katalogu.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing** \> **Katalogi** \> **Katalogi dostawców** i kliknij dwukrotnie katalog, na którym chcesz pracować.

2. Pobierz bieżący szablon importu katalogu (plik XSD). Na stronie **Aktualizowanie katalogu** w **okienku akcji** na karcie **Katalogi** w grupie **Informacje pokrewne** kliknij przycisk **Generowanie szablonu katalogu** i wybierz opcję **Kategoria zaopatrzenia**.

    - Za pomocą opcji **Kategoria zaopatrzenia** można wygenerować szablon katalogu obejmujący kategorie zaopatrzenia, w przypadku których dostawca jest upoważniony do dostarczania produktów.

3. W oknie dialogowym **Zapisz jako** wybierz lokalizację, gdzie ma być przechowywany szablon pliku katalogu, i zapisz plik.

Aby uzyskać więcej informacji i przykłady, zobacz ten wpis na blogu: [Katalogi dostawców w systemie Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/)

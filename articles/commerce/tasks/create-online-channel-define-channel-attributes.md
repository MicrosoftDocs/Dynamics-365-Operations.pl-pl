---
title: Tworzenie kanału online i definiowanie atrybutów kanału
description: Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.
author: jashanno
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 98d218a2d4f3b31084adfbc013dd0999f459dc1572e29a6470edc7cb899809c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713373"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Tworzenie kanału online i definiowanie atrybutów kanału

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej. Aby można było utworzyć nowy kanał online, należy najpierw utworzyć hierarchię organizacyjną. Procedura wykorzystuje dane firmy demonstracyjnej USRT.


## <a name="create-a-new-online-channel"></a>Tworzenie nowego kanału online
1. Wybierz kolejno opcje Commerce > Kanały > Sklepy internetowe.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. W polu Magazyn wprowadź lub wybierz wartość.
5. W polu Strefa czasowa sklepu wybierz opcję.
6. W polu Domyślny odbiorca wprowadź lub wybierz wartość.
7. W polu Książka adresowa odbiorców wprowadź lub wybierz wartość.
8. W polu Warunki płatności wprowadź lub wybierz wartość.
9. W polu Metoda płatności wprowadź lub wybierz wartość.
10. W polu Profil powiadomienia pocztą e-mail wprowadź lub wybierz wartość.
11. Rozwiń sekcję Wymiary finansowe.
12. W polu BusinessUnit wprowadź lub wybierz wartość.
    * Podobnie można ustawić wartości dla wszystkich innych wymiarów domyślnych.  
13. Kliknij przycisk Zapisz.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Dodawanie kanału online do hierarchii organizacyjnej
1. Zamknij stronę.
2. Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Hierarchie organizacyjne.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Kliknij przycisk Wyświetl.
5. Kliknij przycisk Edytuj.
    * Można wybrać dowolny węzeł hierarchii, aby wstawić w nim nowy kanał.  
6. Kliknij przycisk Wstaw.
7. Kliknij opcję kanał Commerce.
8. Kliknij przycisk OK.
9. Kliknij przycisk Publikuj, aby otworzyć rozwijane okno dialogowe.
10. W polu Data obowiązywania wprowadź datę i godzinę.
11. Kliknij przycisk Publikuj.

## <a name="configure-orders-for-near-real-time-notification"></a>Konfigurowanie zamówień w celu powiadamiania w czasie zbliżonym do rzeczywistego
1. Wybierz kolejno opcje Commerce > Ustawienia Headquarters > Parametry > Parametry Commerce.
2. Zmień ustawienie opcji Użyj usługi czasu rzeczywistego dla tworzenia zamówień handlu elektronicznego na „Tak”.
3. Wykonaj harmonogram dystrybucji 1070, aby zsynchronizować zmiany z bazą danych kanału. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
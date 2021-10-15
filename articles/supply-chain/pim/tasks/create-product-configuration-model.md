---
title: Tworzenie modelu konfiguracji produktu
description: W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568431"
---
# <a name="create-a-product-configuration-model"></a>Tworzenie modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-product-model"></a>Tworzenie modelu produktu

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Opis** wpisz wartość.
1. W polu **Strategia zmiennej** wybierz opcję.
    * Strategia zmiennej określa sposób przetwarzania ograniczeń w modelu konfiguracji produktu opartej na ograniczeniach. Wybranie tej opcji może mieć wpływ na działanie modelu konfiguracji produktu.  
1. W polu **Nazwa** wpisz wartość.
    * Składnik główny reprezentuje modelu konfiguracji produktu, ale może być używany również w innych modelach produktów.  
1. Kliknij przycisk **OK**.
1. W polu **Użyj ponownie konfiguracji** wybierz opcję.
    * Jeśli parametr Użyj ponownie konfiguracji jest ustawiony na Tak, system będzie sprawdzał istnienie identycznych konfiguracji po każdej sesji konfigurowania i wykorzystywał je, jeśli znajdzie dokładne odpowiedniki.  

## <a name="add-attributes"></a>Dodaj atrybuty

1. Rozwiń sekcję **Atrybuty**.
2. Wybierz opcję **Dodaj**.
3. Na liście oznacz wybrany wiersz.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Nazwa zmiennej** wpisz wartość.
    * Nazwa zmiennej jest używana przez solver ograniczeń w konfiguratorze produktów. Nie może zawierać spacji ani znaków specjalnych, z wyjątkiem _(podkreślenia).  
6. W polu **Opis** wpisz wartość.
    * Tekst opisu jest wyświetlany użytkownikowi konfiguracji i dlatego może służyć jako pomoc przy wyborze odpowiedniej wartość atrybutu.  
7. W polu **Typ atrybutu** wprowadź lub wybierz wartość.
    * Typ atrybutu określa, które wartości są dostępne dla atrybutu.  
8. Zaznacz pole wyboru **Uwzględnij w ponownym użyciu**.
    * Ta opcja jest dostępna tylko po zaznaczeniu opcji Użyj ponownie konfiguracji. Zaznaczenie pola wyboru Uwzględnij w ponownym użyciu spowoduje, że atrybut będzie brany pod uwagę, gdy system szuka dokładnie pasującego elementu.  

## <a name="add-subcomponents"></a>Dodawanie podskładników

1. Rozwiń sekcję **Składniki podrzędne**.
2. Wybierz opcję **Dodaj**.
3. Na liście oznacz wybrany wiersz.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Nazwa zmiennej** wpisz wartość.
6. W polu **Opis** wpisz wartość.
7. W polu **Składnik** wprowadź lub wybierz wartość.
    * Każdy podskładnik musi się odwoływać do definicji składnika. Ten projekt obsługuje składniki wielokrotnego użytku i zapewnia, że po zdefiniowaniu składnika będzie go może używać w wielu modelach produktów.  
8. Wybierz opcję **Zapisz**.
9. Wybierz opcję **Szczegóły wiersza BOM**.
    * Formularz Szczegóły wiersza BOM pozwala użytkownikowi wybrać wymagane właściwości podskładnika. Każdej właściwości można nadać stałą wartość lub zmapować ją na atrybut. Mapowanie na atrybut spowoduje, że właściwość wiersza BOM będzie otrzymywać różne wartości w zależności od wybranej konfiguracji.  
10. W polu **Kod towaru** wpisz lub wprowadź wartość.
    * Każdy podskładnik reprezentuje konfigurowalny produkt główny z technologią konfiguracji opartej na ograniczeniach. Odwoływanie odbywa się za pomocą numeru towaru.  
11. Zaznacz pole wyboru **Ustaw**.
12. W polu **Obliczanie** wybierz opcję **Tak**.
    * Ustawienie opcji obliczania zapewnia, że produkt będzie uwzględniany przy wykonywaniu obliczeń kosztów dla produktu.  
13. Kliknij kartę **Konfiguracja**.
14. Zaznacz pole wyboru **Ustaw**.
15. W polu **Ilość** wpisz liczbę.
    * Pole ilości określa, jaka część tego produktu będzie zużywana w skonfigurowanym produkcie.  
16. Zaznacz pole wyboru **Ustaw**.
17. W polu **W serii** wprowadź liczbę.
18. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
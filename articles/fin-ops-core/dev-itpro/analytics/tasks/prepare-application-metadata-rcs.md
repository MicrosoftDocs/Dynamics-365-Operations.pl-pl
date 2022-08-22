---
title: Przygotowywanie metadanych aplikacji używanych w RCS
description: W tym artykule opisano sposób tworzenia nowej konfiguracji raportowania zawierającej metadane aplikacji.
author: kfend
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: a9ccbb120be43eaf7a8ae8b5bf8eaafb4850b199
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289983"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Przygotowywanie metadanych aplikacji używanych w RCS
[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób, w jaki użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą metadane aplikacji w celu projektowania konfiguracji mapowania modeli ER w usłudze Regulatory configuration service (RCS). Ta konfiguracja będzie używana do projektowania konfiguracji mapowania przykładowego modelu ER w celu uzyskania dostępu do transakcji handlu zagranicznego.  W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki te można wykonać w dowolnej firmie. Aby wykonać te kroki, należy najpierw wykonać kroki w artykule [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="prerequisites"></a>Wymagania wstępne
1.    Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**. 
2.    Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md). 
3.    Kliknij przycisk **Konfiguracje metadanych**. 
4.    Załóżmy, że oprogramowanie RCS zostanie użyte do zaprojektowania rozwiązania ER dla aplikacji finansowej i operacyjnej, która będzie generować dokumenty elektroniczne zawierające informacje z domeny biznesowej handlu zagranicznego. Aby określić mapowanie między modelem danych ER a źródłami wymaganych danych, w oprogramowaniu RCS musi mieć dostęp do metadanych aplikacji Finanse i operacje. Dlatego w ramach projektowania rozwiązania ER konfigurowana jest nowa konfiguracja metadanych ER zawierającą wszystkie metadane, które są obecnie wymagane w przypadku generowania raportów ER dla wybranej domeny biznesowej. 

## <a name="add-metadata-configuration"></a>Dodaj konfigurację metadanych 
1.    Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. 
2.    W polu **Nazwa** wpisz „Metadane handlu zagranicznego”. 
3.    Kliknij przycisk **Utwórz konfigurację**. 
4.    Kliknij przycisk **Konstruktor**. 
5.    Kliknij przycisk **Dodaj**. 
  
> [!NOTE]
> Można wybrać wszystkie metadane dla całej aplikacji lub dla wybranych modeli lub wybranych modułów. Należy pamiętać, że w tym przypadku zostaną automatycznie dodane następujące metadane: tabele rekordów, wyliczenia i rozszerzone typy danych. Gdy są potrzebne dodatkowe typy metadanych, należy je dodać ręcznie. 
 
Istnieją metadane związane z transakcjami handlu zagranicznego przez wybranie elementów metadanych ręcznie. 
  
6.    Kliknij opcję **Dodaj źródło danych**. 
7.    Kliknij **Rekordy tabeli**. 
8.    Użyj szybkiego filtru, aby wyfiltrować pole **Nazwa** według wartości „intrastat”. 
9.    Wybierz tabelę **Intrastat**. 
10.    Kliknij przycisk **OK**.
  
Dodano informacje metadanych dotyczące tabeli rekordów Intrastat. 
  
11.    W drzewie rozwiń **Tabele rekordów Intrastat**\>**Relacje**. 
12.    W drzewie wybierz pozycję **Tabela rekordów Intrastat**\>**Relacje\IntrastatCommodity (tabela rekordów EcoResCategory)**.     
13.    Kliknij przycisk **Dodaj metadane** 
  
> [!NOTE]
> Metadane dotyczące relacji wymaganych dla wybranych tabel muszą zostać dodane ręcznie. 
  
16.    Kliknij opcję **Dodaj źródło danych**. 
17.    Kliknij przycisk **Wyliczenie**. 
18.    Użyj szybkiego filtru, aby wyfiltrować pole **Nazwa** według wartości „IntrastatKierunek". 
19.    Wybierz rekord **IntrastatDirection wyliczenia**. 
20.    Kliknij przycisk **OK**. 
21.    Kliknij przycisk **Zapisz**.  
22.    Zamknij stronę. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Zakończ wersję roboczą konfiguracji metadanych
1.    Kliknij przycisk **Zmień stan**. 
2.    Kliknij przycisk **Wykonaj.** 
3.    Kliknij przycisk **OK**. 
4.    Wybierz ukończoną wersję **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Eksportowanie ukończonej wersji konfiguracji metadanych z aplikacji jako pliku XML
1.    Kliknij opcję **Wymiana**. 
2.    Kliknij przycisk **Eksportuj jako plik XML**. 
3.    Kliknij przycisk **OK**. 
    
Utworzona konfiguracja metadanych ER została zapisana jako plik XML, który można importować do RCS i użyć jako źródło informacji o metadanych dla domeny biznesowej w handlu zagranicznym. Na podstawie tych informacji można określić mapowanie między metadanymi aplikacji a modelem danych ER.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

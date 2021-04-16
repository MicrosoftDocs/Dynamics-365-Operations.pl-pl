---
title: Typ miejsca docelowego modelu archiwizacji
description: Ten temat zawiera informacje dotyczące konfigurowania miejsca docelowego archiwum dla każdego składnika typu FOLDER lub PLIK w formacie raportowania elektronicznego (ER).
author: NickSelin
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 18c662fee0cedaa55f63ffeb25b0d61ee7baffda
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753535"
---
# <a name="archive-er-destination-type"></a>Typ miejsca docelowego modelu archiwizacji

[!include [banner](../includes/banner.md)]

Możesz konfigurować lokalizację docelową archiwum dla poszczególnych składników **Folder** lub **Plik** formatu raportowania elektronicznego (ER) skonfigurowanego do generowania dokumentów wychodzących. Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest przechowywany jako załącznik do rekordu listy zadań ER. Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**.

Ta opcja służy do wysyłania wygenerowanego dokumentu do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure. W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu. Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**. Definiowanie typów dokumentów odbywa się w oknie [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Typy dokumentów**. Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.

[![Strona Typy dokumentów](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Lokalizacja określa, gdzie plik jest zapisywany. Po włączeniu miejsca docelowego **Archiwum** wyniki mogą być zapisywane w archiwum zadania. Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarchiwizowane zadania raportowania elektronicznego**.

> [!NOTE]
> Wybierz typ dokumentu dla archiwum zadań poprzez przejście do sekcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** \> **Parametry raportowania elektronicznego**. Aby uzyskać więcej informacji, zobacz [Konfigurowanie struktury modułu Raportowanie elektroniczne (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Plik można zapisać w wyznaczonym folderze programu SharePoint. Domyślny serwer programu SharePoint definiuje się w oknie **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Parametry zarządzania dokumentami**. Na karcie **SharePoint**, skonfiguruj folder SharePoint. Następnie można wybrać tę opcję jako folder, w którym zostanie zapisana produkcja globalna ER. W **SharePoint** w tym typie dokumentu należy wybrać lokalizację.

[![Wybieranie folderu programu SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Magazyn Azure

Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Magazyn Azure**, można zapisać plik do magazynu usługi Azure.

> [!NOTE] 
> Struktura modułu ER trwale przechowuje pliki w magazynie obiektów Blob systemu Azure, w przeciwieństwie do struktury zarządzania danymi, która stosuje zasadę przechowywania przez siedem dni dla dokumentów, które muszą zostać przetworzone. Aby uzyskać więcej informacji, zobacz [Interfejs API pobierania informacji o stanie wiadomości](../data-entities/recurring-integrations.md#api-for-getting-message-status) i [Interfejs API sprawdzania stanu](../data-entities/data-management-api.md#status-check-api). Pliki powiązane z modułem ER będą przechowywane w magazynie obiektów Blob platformy Azure jako załączniki do rekordów tabeli aplikacji tak długo, jak jest to konieczne. Plik jest usuwany z magazynu obiektów Blob systemu Azure wraz z rekordem tabeli aplikacji, do którego był dołączony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Konfigurowanie zarządzania dokumentami](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
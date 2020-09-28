---
title: Typ miejsca docelowego modelu archiwizacji
description: Ten temat zawiera informacje dotyczące konfigurowania lokalizacji docelowej archiwum dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745592"
---
# <a name="archive-destination"></a>Archiwalne miejsce docelowe

[!include [banner](../includes/banner.md)]

Możesz konfigurować lokalizacje docelową archiwum dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących. Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest przechowywany jako załącznik do rekordu listy zadań ER.

Ta opcja służy do wysyłania wygenerowanego dokumentu do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure. W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu. Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**. Definiowanie typów dokumentów odbywa się w oknie [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Typy dokumentów**. Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.

[![Strona Typy dokumentów](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Lokalizacja określa, gdzie plik jest zapisywany. Po włączeniu miejsca docelowego **Archiwum** wyniki mogą być zapisywane w archiwum zadania. Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarchiwizowane zadania raportowania elektronicznego**.

> [!NOTE]
> Wybierz typ dokumentu dla archiwum zadań poprzez przejście do sekcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** \> **Parametry raportowania elektronicznego**. Aby uzyskać więcej informacji, zobacz [Zmiana konfiguracji ram raportowania elektronicznego (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Plik można zapisać w wyznaczonym folderze programu SharePoint. Domyślny serwer programu SharePoint definiuje się w oknie **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Parametry zarządzania dokumentami**. Na karcie **SharePoint**, skonfiguruj folder SharePoint. Następnie można wybrać tę opcję jako folder, w którym zostanie zapisana produkcja globalna ER. W **SharePoint** w tym typie dokumentu należy wybrać lokalizację.

[![Wybieranie folderu programu SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Magazyn Azure

Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Magazyn Azure**, można zapisać plik do magazynu usługi Azure.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Konfigurowanie zarządzania dokumentami](../../fin-ops/organization-administration/configure-document-management.md)

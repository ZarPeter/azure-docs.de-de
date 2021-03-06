---
title: Attributgruppen im XML-Schema des Dienstmodells
description: Hier werden Attributgruppen im XML-Schema des Service Fabric-Dienstmodells beschrieben.
ms.topic: reference
ms.date: 12/10/2018
ms.openlocfilehash: 95e19dbdeafdd03af56acaeeb06901a36f2e0333
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "75609382"
---
<!-- This article was generated by the Python script found in the service-fabric-service-model-schema.md file -->

# <a name="service-model-xml-schema-attribute-groups"></a>Attributgruppen im XML-Schema des Dienstmodells

## <a name="accountcredentialsgroup-attributegroup"></a>attributeGroup: AccountCredentialsGroup

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|AccountCredentialsGroup|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="AccountCredentialsGroup">
        <xs:attribute name="AccountName" type="xs:string" use="optional">
          <xs:annotation>
            <xs:documentation>User name or Service Account Name (for example, MyMachine\JohnDoe or John.Doe@department.contoso.com).</xs:documentation>
          </xs:annotation>
        </xs:attribute>
        <xs:attribute name="Password" type="xs:string" use="optional">
            <xs:annotation>
                <xs:documentation>Password for the user account.</xs:documentation>
            </xs:annotation>
        </xs:attribute>
    </xs:attributeGroup>
    
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="accountname"></a>AccountName
Benutzername oder Dienstkontoname (z.B. „MyMachine\JohnDoe“ oder „John.Doe@department.contoso.com“).

|attribute|value|
|---|---|
|name|AccountName|
|type|xs:string|
|use|optional|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="AccountName" type="xs:string" use="optional">
          <xs:annotation>
            <xs:documentation>User name or Service Account Name (for example, MyMachine\JohnDoe or John.Doe@department.contoso.com).</xs:documentation>
          </xs:annotation>
        </xs:attribute>
        
```

#### <a name="password"></a>Kennwort
Kennwort für das Benutzerkonto.

|attribute|value|
|---|---|
|name|Kennwort|
|type|xs:string|
|use|optional|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Password" type="xs:string" use="optional">
            <xs:annotation>
                <xs:documentation>Password for the user account.</xs:documentation>
            </xs:annotation>
        </xs:attribute>
    
```

## <a name="applicationinstanceattrgroup-attributegroup"></a>attributeGroup: ApplicationInstanceAttrGroup
Die Attributgruppe für die Anwendungsinstanz

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|ApplicationInstanceAttrGroup|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ApplicationInstanceAttrGroup">
    <xs:annotation>
      <xs:documentation>Attribute group for application instance.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="NameUri" type="FabricUri" use="required">
      <xs:annotation>
        <xs:documentation>Fully qualified name of the application.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
    <xs:attribute name="ApplicationId" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>Id of this application.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="nameuri"></a>NameUri
Vollständig qualifizierter Name der Anwendung

|attribute|value|
|---|---|
|name|NameUri|
|type|FabricUri|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="NameUri" type="FabricUri" use="required">
      <xs:annotation>
        <xs:documentation>Fully qualified name of the application.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
    
```

#### <a name="applicationid"></a>ApplicationId
Die ID dieser Anwendung

|attribute|value|
|---|---|
|name|ApplicationId|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ApplicationId" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>Id of this application.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="applicationmanifestattrgroup-attributegroup"></a>attributeGroup: ApplicationManifestAttrGroup
Die Attributgruppe für das Anwendungsmanifest

|attribute|value|
|---|---|
|Inhalt|3 Attribut(e)|
|name|ApplicationManifestAttrGroup|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ApplicationManifestAttrGroup">
    <xs:annotation>
      <xs:documentation>Attribute group for application manifest.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="ApplicationTypeName" use="required">
      <xs:annotation>
        <xs:documentation>The type identifier for this application.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="ApplicationTypeVersion" use="required">
      <xs:annotation>
        <xs:documentation>The version of this application type, an unstructured string.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="ManifestId" use="optional" default="" type="xs:string">
      <xs:annotation>
        <xs:documentation>The identifier of this application manifest, an unstructured string.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
    <xs:anyAttribute processContents="skip"/> <!-- Allow unknown attributes to be used. -->
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="applicationtypename"></a>ApplicationTypeName
Der Typbezeichner für diese Anwendung

|attribute|value|
|---|---|
|name|ApplicationTypeName|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ApplicationTypeName" use="required">
      <xs:annotation>
        <xs:documentation>The type identifier for this application.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    
```

#### <a name="applicationtypeversion"></a>ApplicationTypeVersion
Die Version dieses Anwendungstyps, eine nicht strukturierte Zeichenfolge.

|attribute|value|
|---|---|
|name|ApplicationTypeVersion|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ApplicationTypeVersion" use="required">
      <xs:annotation>
        <xs:documentation>The version of this application type, an unstructured string.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    
```

#### <a name="manifestid"></a>ManifestId
Der Bezeichner dieses Anwendungsmanifests, eine nicht strukturierte Zeichenfolge.

|attribute|value|
|---|---|
|name|ManifestId|
|use|optional|
|default||
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ManifestId" use="optional" default="" type="xs:string">
      <xs:annotation>
        <xs:documentation>The identifier of this application manifest, an unstructured string.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
    
```

## <a name="configoverridesidentifier-attributegroup"></a>attributeGroup: ConfigOverridesIdentifier
Identifiziert Konfigurationsaußerkraftsetzungen für ein Dienstpaket.

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|ConfigOverridesIdentifier|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ConfigOverridesIdentifier">
    <xs:annotation>
      <xs:documentation>Identifies configuration overrides for a service package.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="ServicePackageName" type="xs:string" use="required"/>
    <xs:attribute name="RolloutVersion" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>ID of the rollout in which changes were made to the overrides element.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="servicepackagename"></a>ServicePackageName

|attribute|value|
|---|---|
|name|ServicePackageName|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ServicePackageName" type="xs:string" use="required"/>
    
```

#### <a name="rolloutversion"></a>RolloutVersion
Die ID des Rollouts, in dem Änderungen am Überschreibungselement vorgenommen wurden

|attribute|value|
|---|---|
|name|RolloutVersion|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="RolloutVersion" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>ID of the rollout in which changes were made to the overrides element.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="connectionstring-attributegroup"></a>attributeGroup: ConnectionString

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|ConnectionString|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ConnectionString">
                <xs:attribute name="ConnectionString" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Connection string to the Azure storage account. Format: DefaultEndpointsProtocol=https;AccountName=[];AccountKey=[]</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="connectionstring"></a>ConnectionString
Verbindungszeichenfolge für das Azure-Speicherkonto. Format: DefaultEndpointsProtocol=https;AccountName=[];AccountKey=[]

|attribute|value|
|---|---|
|name|ConnectionString|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ConnectionString" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Connection string to the Azure storage account. Format: DefaultEndpointsProtocol=https;AccountName=[];AccountKey=[]</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="containername-attributegroup"></a>attributeGroup: ContainerName

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|ContainerName|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ContainerName">
    <xs:attribute name="ContainerName" type="xs:string">
      <xs:annotation>
        <xs:documentation>The name of the container in Azure blob storage where data is uploaded.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="containername"></a>ContainerName
Der Name des Containers in Azure Blob Storage, in den Daten hochgeladen werden

|attribute|value|
|---|---|
|name|ContainerName|
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ContainerName" type="xs:string">
      <xs:annotation>
        <xs:documentation>The name of the container in Azure blob storage where data is uploaded.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="datadeletionageindays-attributegroup"></a>attributeGroup: DataDeletionAgeInDays

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|DataDeletionAgeInDays|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="DataDeletionAgeInDays">
    <xs:attribute name="DataDeletionAgeInDays" type="xs:string">
      <xs:annotation>
        <xs:documentation>Number of days after which old data is deleted from this location.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="datadeletionageindays"></a>DataDeletionAgeInDays
Anzahl der Tage, nach denen alte Daten aus diesem Speicherort gelöscht werden

|attribute|value|
|---|---|
|name|DataDeletionAgeInDays|
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="DataDeletionAgeInDays" type="xs:string">
      <xs:annotation>
        <xs:documentation>Number of days after which old data is deleted from this location.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="isenabled-attributegroup"></a>IsEnabled attributeGroup

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|isEnabled|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="IsEnabled">
                <xs:attribute name="IsEnabled" type="xs:string">
                        <xs:annotation>
                                <xs:documentation>Whether or not data transfer to this destination is enabled. By default, it is not enabled.</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        </xs:attributeGroup>
        
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="isenabled"></a>isEnabled
Gibt an, ob die Datenübertragung an dieses Ziel aktiviert ist. Standardmäßig ist sie nicht aktiviert.

|attribute|value|
|---|---|
|name|isEnabled|
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="IsEnabled" type="xs:string">
                        <xs:annotation>
                                <xs:documentation>Whether or not data transfer to this destination is enabled. By default, it is not enabled.</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        
```

## <a name="levelfilter-attributegroup"></a>attributeGroup: LevelFilter

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|LevelFilter|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="LevelFilter">
    <xs:attribute name="LevelFilter" type="xs:string">
      <xs:annotation>
        <xs:documentation>Level at which ETW events should be filtered. All events at the same or lower level than the specified level are included.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="levelfilter"></a>LevelFilter
Die Ebene, auf der ETW-Ereignisse gefiltert werden sollen. Alle Ereignisse auf der gleichen oder einer niedrigeren als der angegebenen Ebene werden einbezogen.

|attribute|value|
|---|---|
|name|LevelFilter|
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="LevelFilter" type="xs:string">
      <xs:annotation>
        <xs:documentation>Level at which ETW events should be filtered. All events at the same or lower level than the specified level are included.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="namevaluepair-attributegroup"></a>attributeGroup: NameValuePair
Name und Wert werden als ein Attribut definiert.

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|NameValuePair|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="NameValuePair">
    <xs:annotation>
      <xs:documentation>Name and Value defined as an attribute.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="Name" use="required">
      <xs:annotation>
        <xs:documentation>The name of the setting to override.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="Value" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>The new value of the setting.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="name"></a>Name
Der Name der zu überschreibenden Einstellung

|attribute|value|
|---|---|
|name|Name|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Name" use="required">
      <xs:annotation>
        <xs:documentation>The name of the setting to override.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    
```

#### <a name="value"></a>value
Der neue Wert der Einstellung

|attribute|value|
|---|---|
|name|value|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Value" type="xs:string" use="required">
      <xs:annotation>
        <xs:documentation>The new value of the setting.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="path-attributegroup"></a>attributeGroup: Path

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|`Path`|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Path">
                <xs:attribute name="Path" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Path to the file share. Format: file:[]</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        </xs:attributeGroup>
        
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="path"></a>`Path`
Der Pfad zur Dateifreigabe. Format: file:[]

|attribute|value|
|---|---|
|name|`Path`|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Path" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Path to the file share. Format: file:[]</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        
```

## <a name="relativefolderpath-attributegroup"></a>attributeGroup: RelativeFolderPath

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|RelativeFolderPath|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="RelativeFolderPath">
                <xs:attribute name="RelativeFolderPath" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Path to the folder, relative to the application log directory.</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        </xs:attributeGroup>
        
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="relativefolderpath"></a>RelativeFolderPath
Pfad zum Ordner, relativ zum Verzeichnis des Anwendungsprotokolls.

|attribute|value|
|---|---|
|name|RelativeFolderPath|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="RelativeFolderPath" type="xs:string" use="required">
                        <xs:annotation>
                                <xs:documentation>Path to the folder, relative to the application log directory.</xs:documentation>
                        </xs:annotation>
                </xs:attribute>
        
```

## <a name="servicemanifestidentifier-attributegroup"></a>attributeGroup: ServiceManifestIdentifier
Identifiziert ein Dienstmanifest.

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|ServiceManifestIdentifier|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ServiceManifestIdentifier">
    <xs:annotation>
      <xs:documentation>Identifies a service manifest.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="ServiceManifestName" use="required">
      <xs:annotation>
        <xs:documentation>The name of the service manifest this is referenced. The name must match the Name declared in the ServiceManifest element of the service manifest.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="ServiceManifestVersion" use="required">
      <xs:annotation>
        <xs:documentation>The version of the service manifest that is referenced. The version must match the version declared in the service manifest.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="servicemanifestname"></a>ServiceManifestName
Der Name des Dienstmanifests, auf das verwiesen wird. Der Name muss dem im ServiceManifest-Element des Dienstmanifests deklarierten Namen entsprechen.

|attribute|value|
|---|---|
|name|ServiceManifestName|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ServiceManifestName" use="required">
      <xs:annotation>
        <xs:documentation>The name of the service manifest this is referenced. The name must match the Name declared in the ServiceManifest element of the service manifest.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    
```

#### <a name="servicemanifestversion"></a>ServiceManifestVersion
Die Version des Dienstmanifests, auf das verwiesen wird. Die Version muss der im Dienstmanifest deklarierten Version entsprechen.

|attribute|value|
|---|---|
|name|ServiceManifestVersion|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="ServiceManifestVersion" use="required">
      <xs:annotation>
        <xs:documentation>The version of the service manifest that is referenced. The version must match the version declared in the service manifest.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  
```

## <a name="uploadintervalinminutes-attributegroup"></a>attributeGroup: UploadIntervalInMinutes

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|UploadIntervalInMinutes|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="UploadIntervalInMinutes">
    <xs:attribute name="UploadIntervalInMinutes" type="xs:string">
      <xs:annotation>
        <xs:documentation>Interval in minutes at which data is uploaded to this destination.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="uploadintervalinminutes"></a>UploadIntervalInMinutes
Intervall in Minuten, in dem Daten in dieses Ziel hochgeladen werden

|attribute|value|
|---|---|
|name|UploadIntervalInMinutes|
|type|xs:string|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="UploadIntervalInMinutes" type="xs:string">
      <xs:annotation>
        <xs:documentation>Interval in minutes at which data is uploaded to this destination.</xs:documentation>
      </xs:annotation>
    </xs:attribute>
  
```

## <a name="versioneditemattrgroup-attributegroup"></a>attributeGroup: VersionedItemAttrGroup
Die Attributgruppe für die Versionsangabe von Abschnitten in ApplicationInstance- und ServicePackage-Dokumenten.

|attribute|value|
|---|---|
|Inhalt|1 Attribut(e)|
|name|VersionedItemAttrGroup|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="VersionedItemAttrGroup">
    <xs:annotation>
      <xs:documentation>Attribute group for versioning sections in ApplicationInstance and ServicePackage documents.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="RolloutVersion" type="xs:string" use="required"/>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="rolloutversion"></a>RolloutVersion

|attribute|value|
|---|---|
|name|RolloutVersion|
|type|xs:string|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="RolloutVersion" type="xs:string" use="required"/>
  
```

## <a name="versionedname-attributegroup"></a>attributeGroup: VersionedName
Attributgruppe, die einen Namen und eine Version enthält

|attribute|value|
|---|---|
|Inhalt|2 Attribut(e)|
|name|VersionedName|

### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attributeGroup xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="VersionedName">
    <xs:annotation>
      <xs:documentation>Attribute group that includes a Name and a Version.</xs:documentation>
    </xs:annotation>
    <xs:attribute name="Name" use="required">
      <xs:annotation>
        <xs:documentation>Name of the versioned item.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="Version" use="required">
      <xs:annotation>
        <xs:documentation>Version of the versioned item, an unstructured string.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:attributeGroup>
  
```
### <a name="attribute-details"></a>Attributdetails

#### <a name="name"></a>Name
Name des Elements mit Versionsangabe

|attribute|value|
|---|---|
|name|Name|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Name" use="required">
      <xs:annotation>
        <xs:documentation>Name of the versioned item.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    
```

#### <a name="version"></a>Version
Version des Elements mit Versionsangabe (nicht strukturierte Zeichenfolge)

|attribute|value|
|---|---|
|name|Version|
|use|required|

##### <a name="xml-source"></a>XML-Quelle
```xml
<xs:attribute xmlns:xs="https://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2011/01/fabric" name="Version" use="required">
      <xs:annotation>
        <xs:documentation>Version of the versioned item, an unstructured string.</xs:documentation>
      </xs:annotation>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  
```


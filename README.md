[Untitled Diagram.drawio](https://github.com/user-attachments/files/26736371/Untitled.Diagram.drawio)![automated](https://github.com/user-attachments/assets/32eabdc2-4da2-4a92-bed5-c64271120906)# 🚀 Multi-Tier Java Application Deployment on AWS using Ansible

## 📌 Project Overview[Untitled Diagram.drawio](https://github.com/user-attachments/files/26736309/Untitled.Diagram.drawio)


This project demonstrates deploying a **multi-tier Java web application** on AWS using manual infrastructure (AWS Console) setup and Ansible automation.

The architecture follows a real-world production-like design with separate layers for application, database, caching, messaging, and load balancing.

---

## 🏗️ Architecture Diagram
[Uploading Untitled Diagram<mxfile host="app.diagrams.net">
  <diagram name="AWS Architecture" id="UZ2wIf_bUpgMK8JvVB01">
    <mxGraphModel dx="1051" dy="609" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="t2yceLYg47exxWDcY1l5-1" parent="1" style="image;aspect=fixed;perimeter=ellipsePerimeter;html=1;align=center;shadow=0;dashed=0;spacingTop=3;image=img/lib/active_directory/internet_cloud.svg;fontStyle=1" value="" vertex="1">
          <mxGeometry height="31.5" width="50" x="10" y="419.25" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-6" parent="1" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=1;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_region;strokeColor=#00A4A6;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#147EBA;dashed=1;" value="Region" vertex="1">
          <mxGeometry height="420" width="490" x="270" y="220" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-4" parent="t2yceLYg47exxWDcY1l5-6" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=1;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc2;strokeColor=#8C4FFF;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#AAB7B8;dashed=0;" value="VPC" vertex="1">
          <mxGeometry height="350" width="400" x="50" y="40" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-7" parent="t2yceLYg47exxWDcY1l5-4" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=1;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_availability_zone;strokeColor=#545B64;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#545B64;dashed=1;" value="Availability zone" vertex="1">
          <mxGeometry height="280" width="320" x="30" y="30" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-2" parent="t2yceLYg47exxWDcY1l5-4" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=1;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.internet_gateway;" value="" vertex="1">
          <mxGeometry height="60" width="60" x="-30" y="141" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-19" edge="1" parent="t2yceLYg47exxWDcY1l5-4" source="t2yceLYg47exxWDcY1l5-2" style="edgeStyle=none;orthogonalLoop=1;jettySize=auto;html=1;endArrow=classic;startArrow=classic;endSize=8;startSize=8;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;fontStyle=1" target="t2yceLYg47exxWDcY1l5-7" value="">
          <mxGeometry relative="1" width="100" as="geometry">
            <Array as="points" />
            <mxPoint x="-170" y="190" as="sourcePoint" />
            <mxPoint x="-70" y="190" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-12" parent="1" style="dashed=0;outlineConnect=0;html=1;align=center;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;shape=mxgraph.webicons.java;gradientColor=#DFDEDE;fontStyle=1" value="" vertex="1">
          <mxGeometry height="102.4" width="102.4" x="468.8" y="663.13" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-13" parent="1" style="shape=mxgraph.networks2.icon;aspect=fixed;fillColor=#EDEDED;strokeColor=#000000;gradientColor=#5B6163;network2IconShadow=1;network2bgFillColor=none;labelPosition=center;verticalLabelPosition=bottom;align=center;verticalAlign=top;network2Icon=mxgraph.networks2.laptop;network2IconW=1;network2IconH=0.5734;fontStyle=1" value="" vertex="1">
          <mxGeometry height="28.67" width="50" x="10" y="700" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-14" parent="1" style="shape=rect;fillColor=#EE5396;aspect=fixed;resizable=0;labelPosition=center;verticalLabelPosition=bottom;align=center;verticalAlign=top;strokeColor=none;fontSize=14;fontStyle=1" value="Ansible" vertex="1">
          <mxGeometry height="48" width="48" x="220" y="690.33" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-15" parent="t2yceLYg47exxWDcY1l5-14" style="fillColor=#ffffff;strokeColor=none;dashed=0;outlineConnect=0;html=1;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;part=1;movable=0;resizable=0;rotatable=0;shape=mxgraph.ibm_cloud.logo--ansible-community;fontStyle=1" value="" vertex="1">
          <mxGeometry height="24" relative="1" width="24" as="geometry">
            <mxPoint x="12" y="12" as="offset" />
          </mxGeometry>
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-20" edge="1" parent="1" source="t2yceLYg47exxWDcY1l5-13" style="edgeStyle=none;orthogonalLoop=1;jettySize=auto;html=1;rounded=0;exitX=0.975;exitY=0.406;exitDx=0;exitDy=0;exitPerimeter=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;fontStyle=1" target="t2yceLYg47exxWDcY1l5-14" value="">
          <mxGeometry relative="1" width="100" as="geometry">
            <Array as="points" />
            <mxPoint x="70" y="708.3399999999999" as="sourcePoint" />
            <mxPoint x="170" y="708.3399999999999" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-21" edge="1" parent="1" source="t2yceLYg47exxWDcY1l5-14" style="edgeStyle=none;orthogonalLoop=1;jettySize=auto;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;fontStyle=1" value="">
          <mxGeometry relative="1" width="100" as="geometry">
            <Array as="points" />
            <mxPoint x="358.8" y="713.8" as="sourcePoint" />
            <mxPoint x="458.8" y="713.8" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-8" parent="1" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=1;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;grStroke=0;strokeColor=#7AA116;fillColor=#F2F6E8;verticalAlign=top;align=left;spacingLeft=30;fontColor=#248814;dashed=0;" value="Public subnet" vertex="1">
          <mxGeometry height="190" width="220" x="400" y="330" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-9" parent="t2yceLYg47exxWDcY1l5-8" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=1;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_ec2_instance_contents;strokeColor=#D86613;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#D86613;dashed=0;" value="EC2 instance contents" vertex="1">
          <mxGeometry height="50" width="80" x="80" y="80" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-24" parent="t2yceLYg47exxWDcY1l5-8" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontStyle=1" value="security group" vertex="1">
          <mxGeometry height="30" width="60" x="80" y="32" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-25" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontStyle=1" value="Developer" vertex="1">
          <mxGeometry height="30" width="60" x="5" y="735.53" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-26" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontStyle=1" value="IGS" vertex="1">
          <mxGeometry height="30" width="60" x="149" y="480" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-27" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontStyle=1" value="Internet" vertex="1">
          <mxGeometry height="30" width="60" x="5" y="460" as="geometry" />
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-29" edge="1" parent="1" source="t2yceLYg47exxWDcY1l5-12" style="endArrow=classic;html=1;rounded=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;fontStyle=1" target="t2yceLYg47exxWDcY1l5-9" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="250" y="510" as="sourcePoint" />
            <mxPoint x="300" y="460" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="t2yceLYg47exxWDcY1l5-30" edge="1" parent="1" source="t2yceLYg47exxWDcY1l5-1" style="endArrow=classic;startArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;fontStyle=1" target="t2yceLYg47exxWDcY1l5-9" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="170" y="470" as="sourcePoint" />
            <mxPoint x="220" y="420" as="targetPoint" />
          </mxGeometry>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
.drawio…]()


---

## ☁️ AWS Infrastructure

### 🔹 VPC

* CIDR: `10.0.0.0/16`

### 🔹 Subnets

| Layer        | CIDR        |
| ------------ | ----------- |
| App          | 10.0.1.0/24 |
| DB           | 10.0.2.0/24 |
| Memcache     | 10.0.3.0/24 |
| RabbitMQ     | 10.0.4.0/24 |
| LoadBalancer | 10.0.5.0/24 |

### 🔹 Networking

* Internet Gateway attached to VPC
* Route Table:

  * Public Subnets: App, LoadBalancer
  * Private Subnets: DB, Memcache, RabbitMQ

---

## 🔐 Security Groups

| Security Group | Rules                           |
| -------------- | ------------------------------- |
| app-sg         | 8080 from lb-sg, SSH from my IP |
| db-sg          | 3306 from app-sg                |
| memcache-sg    | 11211 from app-sg               |
| rabbit-sg      | 5672 from app-sg                |
| lb-sg          | 80 from anywhere                |

---

## 🖥️ EC2 Instances

| Role         | Private IP |
| ------------ | ---------- |
| App          | 10.0.1.10  |
| DB           | 10.0.2.10  |
| Memcache     | 10.0.3.10  |
| RabbitMQ     | 10.0.4.10  |
| LoadBalancer | 10.0.5.10  |
| Control Node | 10.0.1.100 |

## 📌 Project Overview

* **Terraform**: Used to provision AWS infrastructure, including creating EC2 instances and handling initial setup such as copying required application files to the server.

* **Ansible**: Used for configuration management and application deployment. It installs Web App on the EC2 instance , and runs the application.




## 🎯 Key Learnings

* AWS Networking (VPC, Subnets, IGW)
* Security Groups Design
* Multi-Tier Architecture
* Infrastructure Automation using Ansible
* Deploying Java Applications



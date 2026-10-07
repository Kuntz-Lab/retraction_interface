# retraction_interface

ROS 2 (Jazzy) messages and services for the tissue retraction workspace.

## Services

### `GenerateGoalPointCloud`

Predicts a goal point cloud for a tissue point cloud, given a context point cloud. Served by `diffdef_service_node` in `diffdef_pkg`.

| Field | Type | Description |
| --- | --- | --- |
| `tissue_pointcloud` (request) | `sensor_msgs/PointCloud2` | Current (start) shape of the tissue. |
| `context_pointcloud` (request) | `sensor_msgs/PointCloud2` | Context point cloud the goal is conditioned on. |
| `goal_pointcloud` (response) | `sensor_msgs/PointCloud2` | Predicted goal cloud, with `tissue_pointcloud`'s header. Empty if `success` is false. |
| `success` (response) | `bool` | Whether a goal was generated. |
| `message` (response) | `string` | Reason for failure, or a short summary on success. |

## Build

```bash
source /opt/ros/jazzy/setup.bash
cd ~/retraction_ws
colcon build --packages-select retraction_interface
```

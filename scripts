extends CharacterBody3D

# 移动速度，编辑器可直接修改
@export var move_speed: float = 5.0

func _physics_process(delta: float) -> void:
    # 获取移动输入
    var input_vec: Vector2 = Input.get_vector("move_left", "move_right", "move_forward", "move_backward")
    var move_dir: Vector3 = (transform.basis * Vector3(input_vec.x, 0, input_vec.y)).normalized()

    # 执行移动
    velocity = move_dir * move_speed
    move_and_slide()

    # 角色朝向移动方向
    if move_dir.length() > 0.1:
        look_at(global_position + move_dir, Vector3.UP)
